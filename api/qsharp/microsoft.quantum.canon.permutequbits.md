---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Operación PermuteQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 0f4d8819d5b08f4d5370f8fdc407b2eb2a3e5f21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728481"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="079aa-102">Operación PermuteQubits</span><span class="sxs-lookup"><span data-stu-id="079aa-102">PermuteQubits operation</span></span>

<span data-ttu-id="079aa-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="079aa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="079aa-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="079aa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="079aa-105">Se silencia qubits mediante la operación de intercambio.</span><span class="sxs-lookup"><span data-stu-id="079aa-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="079aa-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="079aa-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="079aa-107">ordenación: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="079aa-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="079aa-108">Describe la nueva ordenación de qubits, donde el qubit en el índice ahora estará en el orden [i].</span><span class="sxs-lookup"><span data-stu-id="079aa-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="079aa-109">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="079aa-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="079aa-110">Registro de qubit en el que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="079aa-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="079aa-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="079aa-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

