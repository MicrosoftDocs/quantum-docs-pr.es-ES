---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Operación ApplyMajorityInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843723"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="56d40-102">Operación ApplyMajorityInPlace</span><span class="sxs-lookup"><span data-stu-id="56d40-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="56d40-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="56d40-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="56d40-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56d40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56d40-105">Aplica la operación de mayoría de tres qubit en contexto en un registro de qubits.</span><span class="sxs-lookup"><span data-stu-id="56d40-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="56d40-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="56d40-106">Description</span></span>

<span data-ttu-id="56d40-107">Esta operación calcula la función de mayoría en contexto en 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="56d40-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="56d40-108">Si denotamos la salida qubit como $z $ y Qubits de entrada como $x $ y $y $, la operación realiza la transformación siguiente: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="56d40-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="56d40-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="56d40-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="56d40-110">salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="56d40-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="56d40-111">Primera entrada qubit.</span><span class="sxs-lookup"><span data-stu-id="56d40-111">First input qubit.</span></span> <span data-ttu-id="56d40-112">Tenga en cuenta que la salida se calcula en contexto y se almacena en este qubit.</span><span class="sxs-lookup"><span data-stu-id="56d40-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="56d40-113">entrada: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="56d40-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="56d40-114">Segundo y tercer qubits de entrada.</span><span class="sxs-lookup"><span data-stu-id="56d40-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="56d40-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56d40-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

