---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _PQTermToPauliGenIdx_ función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 1f9567f327b5afc3054acbf1a615b44a54453004
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727917"
---
# <a name="_pqtermtopauligenidx_-function"></a><span data-ttu-id="f3dc4-102">_PQTermToPauliGenIdx_ función)</span><span class="sxs-lookup"><span data-stu-id="f3dc4-102">_PQTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="f3dc4-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="f3dc4-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="f3dc4-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3dc4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3dc4-105">Convierte un GeneratorIndex que describe un término de PQ a una expresión ' GeneratorIndex [] ' en términos de Paulis</span><span class="sxs-lookup"><span data-stu-id="f3dc4-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="f3dc4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f3dc4-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="f3dc4-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f3dc4-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f3dc4-108">`GeneratorIndex` que representa un término de PQ.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="f3dc4-109">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="f3dc4-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="f3dc4-110">' GeneratorIndex [] ' que expresa el término de PQ como términos de Pauli.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>