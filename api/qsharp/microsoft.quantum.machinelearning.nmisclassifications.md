---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196317"
---
# <a name="nmisclassifications-function"></a><span data-ttu-id="3c43d-102">NMisclassifications función)</span><span class="sxs-lookup"><span data-stu-id="3c43d-102">NMisclassifications function</span></span>

<span data-ttu-id="3c43d-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3c43d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3c43d-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3c43d-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="3c43d-105">Dado un conjunto de etiquetas inferido y un conjunto de etiquetas correctas, devuelve el número de índices en los que difiere cada conjunto de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="3c43d-105">Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.</span></span>

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a><span data-ttu-id="3c43d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3c43d-106">Input</span></span>

### <a name="proposed--int"></a><span data-ttu-id="3c43d-107">propuesto: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3c43d-107">proposed : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="actual--int"></a><span data-ttu-id="3c43d-108">real: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3c43d-108">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--int"></a><span data-ttu-id="3c43d-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3c43d-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3c43d-110">Número de índices de `idx` este tipo `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="3c43d-110">The number of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>