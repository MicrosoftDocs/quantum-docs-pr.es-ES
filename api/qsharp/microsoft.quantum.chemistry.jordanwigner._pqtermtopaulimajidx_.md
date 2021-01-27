---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliMajIdx_
title: _PQTermToPauliMajIdx_ función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: edb9302e04de2abc6dfa9da0da27504f776e721f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839285"
---
# <a name="_pqtermtopaulimajidx_-function"></a><span data-ttu-id="a2f60-102">_PQTermToPauliMajIdx_ función)</span><span class="sxs-lookup"><span data-stu-id="a2f60-102">_PQTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="a2f60-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a2f60-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a2f60-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a2f60-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="a2f60-105">Convierte un GeneratorIndex que describe un término de PQ a una expresión ' GeneratorIndex [] ' en términos de Paulis</span><span class="sxs-lookup"><span data-stu-id="a2f60-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="a2f60-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a2f60-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="a2f60-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a2f60-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a2f60-108">`GeneratorIndex` que representa un término de PQ.</span><span class="sxs-lookup"><span data-stu-id="a2f60-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="a2f60-109">Salida: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="a2f60-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="a2f60-110">' GeneratorIndex [] ' que expresa el término de PQ como términos de Pauli.</span><span class="sxs-lookup"><span data-stu-id="a2f60-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>