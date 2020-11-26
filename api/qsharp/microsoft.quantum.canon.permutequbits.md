---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Operación PermuteQubits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: deb5fa5b0bc0509c957e01bf22e491ad3e2214f3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205614"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="ce6da-102">Operación PermuteQubits</span><span class="sxs-lookup"><span data-stu-id="ce6da-102">PermuteQubits operation</span></span>

<span data-ttu-id="ce6da-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ce6da-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ce6da-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ce6da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ce6da-105">Se silencia qubits mediante la operación de intercambio.</span><span class="sxs-lookup"><span data-stu-id="ce6da-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ce6da-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ce6da-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="ce6da-107">ordenación: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ce6da-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ce6da-108">Describe la nueva ordenación de qubits, donde el qubit en el índice ahora estará en el orden [i].</span><span class="sxs-lookup"><span data-stu-id="ce6da-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="ce6da-109">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ce6da-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ce6da-110">Registro de qubit en el que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="ce6da-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ce6da-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce6da-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

