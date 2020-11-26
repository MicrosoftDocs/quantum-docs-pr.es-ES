---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 2333dcbd2988480e2b2b9b217b26705f3578de00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230538"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="8afc2-102">IntsToPaulis función)</span><span class="sxs-lookup"><span data-stu-id="8afc2-102">IntsToPaulis function</span></span>

<span data-ttu-id="8afc2-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8afc2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8afc2-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8afc2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8afc2-105">Convierte una matriz de enteros en una matriz de operadores Pauli de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="8afc2-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="8afc2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8afc2-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="8afc2-107">ints: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8afc2-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8afc2-108">Matriz de enteros en el intervalo `0..3`  que se va a convertir en operadores de Pauli.</span><span class="sxs-lookup"><span data-stu-id="8afc2-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="8afc2-109">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="8afc2-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="8afc2-110">Una matriz `paulis` de operadores Pauli `Pauli[]` la misma longitud `ints` que `paulis[idxPauli]` es igual al elemento de `[PauliI, PauliX, PauliY, PauliZ]` proporcionado por `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="8afc2-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>