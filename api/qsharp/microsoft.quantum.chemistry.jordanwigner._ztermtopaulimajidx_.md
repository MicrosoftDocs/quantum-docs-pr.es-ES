---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliMajIdx_
title: _ZTermToPauliMajIdx_ función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 56de7b7b425b7d7c5830c15d7119fc1d0291d061
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839083"
---
# <a name="_ztermtopaulimajidx_-function"></a><span data-ttu-id="63c2d-102">_ZTermToPauliMajIdx_ función)</span><span class="sxs-lookup"><span data-stu-id="63c2d-102">_ZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="63c2d-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="63c2d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="63c2d-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="63c2d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="63c2d-105">Convierte un GeneratorIndex que describe un término Z a una expresión ' GeneratorIndex [] ' en términos de Paulis.</span><span class="sxs-lookup"><span data-stu-id="63c2d-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="63c2d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="63c2d-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="63c2d-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="63c2d-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="63c2d-108">`GeneratorIndex` que representa un término Z.</span><span class="sxs-lookup"><span data-stu-id="63c2d-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="63c2d-109">Salida: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="63c2d-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="63c2d-110">' GeneratorIndex [] ' expresando el término Z como términos Pauli.</span><span class="sxs-lookup"><span data-stu-id="63c2d-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>