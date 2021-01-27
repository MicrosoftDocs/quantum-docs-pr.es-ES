---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 048f91411099d24f3c0c5fd8ae3703779e7ab8a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847903"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="c0b60-102">PauliStringFromGenIdx función)</span><span class="sxs-lookup"><span data-stu-id="c0b60-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="c0b60-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c0b60-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c0b60-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0b60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0b60-105">Extrae la cadena Pauli y sus índices qubit de un término Pauli descrito por `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="c0b60-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="c0b60-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c0b60-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="c0b60-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="c0b60-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="c0b60-108">`GeneratorIndex` tipo que codifica un término Pauli.</span><span class="sxs-lookup"><span data-stu-id="c0b60-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="c0b60-109">Salida: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="c0b60-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="c0b60-110">La cadena Pauli del término descrito por un `GeneratorIndex` y los índices para el qubits en el que actúa.</span><span class="sxs-lookup"><span data-stu-id="c0b60-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>