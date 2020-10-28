---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: b522691d6826933122e2ebac051b15e35b9902e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727857"
---
# <a name="_v0123termtopauligenidx_-function"></a><span data-ttu-id="96dc2-102">_V0123TermToPauliGenIdx_ función)</span><span class="sxs-lookup"><span data-stu-id="96dc2-102">_V0123TermToPauliGenIdx_ function</span></span>

<span data-ttu-id="96dc2-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="96dc2-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="96dc2-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96dc2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96dc2-105">Convierte un GeneratorIndex que describe un término PQRS a una expresión ' GeneratorIndex [] ' en términos de Paulis</span><span class="sxs-lookup"><span data-stu-id="96dc2-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="96dc2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="96dc2-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="96dc2-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="96dc2-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="96dc2-108">`GeneratorIndex` que representa un término PQRS.</span><span class="sxs-lookup"><span data-stu-id="96dc2-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="96dc2-109">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="96dc2-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="96dc2-110">' GeneratorIndex [] ' que expresa el término PQRS como Pauli términos.</span><span class="sxs-lookup"><span data-stu-id="96dc2-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>