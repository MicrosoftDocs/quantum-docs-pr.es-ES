---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliGenIdx
title: _ZTermToPauliGenIdx función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 1569ec742778549b8754cdca8b2d9872310e8976
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727845"
---
# <a name="_ztermtopauligenidx-function"></a><span data-ttu-id="4ce85-102">_ZTermToPauliGenIdx función)</span><span class="sxs-lookup"><span data-stu-id="4ce85-102">_ZTermToPauliGenIdx function</span></span>

<span data-ttu-id="4ce85-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4ce85-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4ce85-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4ce85-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4ce85-105">Convierte un GeneratorIndex que describe un término Z a una expresión ' GeneratorIndex [] ' en términos de Paulis.</span><span class="sxs-lookup"><span data-stu-id="4ce85-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="4ce85-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4ce85-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="4ce85-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4ce85-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="4ce85-108">`GeneratorIndex` que representa un término Z.</span><span class="sxs-lookup"><span data-stu-id="4ce85-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="4ce85-109">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="4ce85-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="4ce85-110">' GeneratorIndex [] ' expresando el término Z como términos Pauli.</span><span class="sxs-lookup"><span data-stu-id="4ce85-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>