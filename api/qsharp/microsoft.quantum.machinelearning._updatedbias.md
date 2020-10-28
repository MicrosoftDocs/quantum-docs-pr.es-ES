---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: _UpdatedBias función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 2704d08e4c1ce868e1fd9065c3cab0285d431094
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731148"
---
# <a name="_updatedbias-function"></a><span data-ttu-id="c8183-102">_UpdatedBias función)</span><span class="sxs-lookup"><span data-stu-id="c8183-102">_UpdatedBias function</span></span>

<span data-ttu-id="c8183-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c8183-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c8183-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c8183-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c8183-105">Devuelve un valor de diferencia que conduce a una puntuación de clasificación incorrecta casi mínima.</span><span class="sxs-lookup"><span data-stu-id="c8183-105">Returns a bias value that leads to near-minimum misclassification score.</span></span>

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a><span data-ttu-id="c8183-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c8183-106">Input</span></span>

### <a name="labeledprobabilities--doubleint"></a><span data-ttu-id="c8183-107">labeledProbabilities: ([Double](xref:microsoft.quantum.lang-ref.double),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="c8183-107">labeledProbabilities : ([Double](xref:microsoft.quantum.lang-ref.double),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>




### <a name="bias--double"></a><span data-ttu-id="c8183-108">bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c8183-108">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="tolerance--double"></a><span data-ttu-id="c8183-109">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c8183-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--double"></a><span data-ttu-id="c8183-110">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c8183-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

