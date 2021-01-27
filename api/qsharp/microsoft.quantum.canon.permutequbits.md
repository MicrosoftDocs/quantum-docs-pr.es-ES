---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Operación PermuteQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 2fbbe0d99ad1383d77cb08ff6b03bcebd8a1971f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852321"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="0b770-102">Operación PermuteQubits</span><span class="sxs-lookup"><span data-stu-id="0b770-102">PermuteQubits operation</span></span>

<span data-ttu-id="0b770-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0b770-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0b770-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b770-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b770-105">Se silencia qubits mediante la operación de intercambio.</span><span class="sxs-lookup"><span data-stu-id="0b770-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0b770-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0b770-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="0b770-107">ordenación: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0b770-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0b770-108">Describe la nueva ordenación de qubits, donde el qubit en el índice ahora estará en el orden [i].</span><span class="sxs-lookup"><span data-stu-id="0b770-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="0b770-109">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0b770-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0b770-110">Registro de qubit en el que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="0b770-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0b770-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b770-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="0b770-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b770-112">Example</span></span>

<span data-ttu-id="0b770-113">Dado el orden = [2, 1, 0] y el registro $ \ket{\ alpha_0} \ket{\ alpha_1} \ket{\ alpha_2} $, PermuteQubits cambia el registro en $ \ket{\ alpha_2} \ket{\ alpha_1} \ket{\ alpha_0} $</span><span class="sxs-lookup"><span data-stu-id="0b770-113">Given ordering = [2, 1, 0] and register $\ket{\alpha_0} \ket{\alpha_1} \ket{\alpha_2}$, PermuteQubits changes the register into $\ket{\alpha_2} \ket{\alpha_1} \ket{\alpha_0}$</span></span>

```qsharp
// The following two lines are equivalent
PermuteQubits([2, 1, 0], register);
SWAP(register[0], register[2]);
```