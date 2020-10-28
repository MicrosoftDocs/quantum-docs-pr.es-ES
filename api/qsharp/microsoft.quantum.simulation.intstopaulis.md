---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725822"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="4d30b-102">IntsToPaulis función)</span><span class="sxs-lookup"><span data-stu-id="4d30b-102">IntsToPaulis function</span></span>

<span data-ttu-id="4d30b-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4d30b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4d30b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4d30b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4d30b-105">Convierte una matriz de enteros en una matriz de operadores Pauli de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="4d30b-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="4d30b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4d30b-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="4d30b-107">ints: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4d30b-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4d30b-108">Matriz de enteros en el intervalo `0..3`  que se va a convertir en operadores de Pauli.</span><span class="sxs-lookup"><span data-stu-id="4d30b-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="4d30b-109">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="4d30b-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="4d30b-110">Una matriz `paulis` de operadores Pauli `Pauli[]` la misma longitud `ints` que `paulis[idxPauli]` es igual al elemento de `[PauliI, PauliX, PauliY, PauliZ]` proporcionado por `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="4d30b-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>