---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 8893d7c5479409a0ff98aa0b9e58f34fd3d274f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839189"
---
# <a name="_v0123termtopauligenidx_-function"></a><span data-ttu-id="725f8-102">_V0123TermToPauliGenIdx_ función)</span><span class="sxs-lookup"><span data-stu-id="725f8-102">_V0123TermToPauliGenIdx_ function</span></span>

<span data-ttu-id="725f8-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="725f8-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="725f8-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="725f8-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="725f8-105">Convierte un GeneratorIndex que describe un término PQRS a una expresión ' GeneratorIndex [] ' en términos de Paulis</span><span class="sxs-lookup"><span data-stu-id="725f8-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="725f8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="725f8-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="725f8-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="725f8-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="725f8-108">`GeneratorIndex` que representa un término PQRS.</span><span class="sxs-lookup"><span data-stu-id="725f8-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="725f8-109">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="725f8-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="725f8-110">' GeneratorIndex [] ' que expresa el término PQRS como Pauli términos.</span><span class="sxs-lookup"><span data-stu-id="725f8-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>