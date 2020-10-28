---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 33da4bc3d7e58b87aef75b453b6af09a51214923
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726290"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="faedf-102">PauliStringFromGenIdx función)</span><span class="sxs-lookup"><span data-stu-id="faedf-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="faedf-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="faedf-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="faedf-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="faedf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="faedf-105">Extrae la cadena Pauli y sus índices qubit de un término Pauli descrito por `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="faedf-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="faedf-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="faedf-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="faedf-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="faedf-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="faedf-108">`GeneratorIndex` tipo que codifica un término Pauli.</span><span class="sxs-lookup"><span data-stu-id="faedf-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="faedf-109">Salida: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="faedf-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="faedf-110">La cadena Pauli del término descrito por un `GeneratorIndex` y los índices para el qubits en el que actúa.</span><span class="sxs-lookup"><span data-stu-id="faedf-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>