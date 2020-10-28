---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Función de clasificación incorrecta
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732980"
---
# <a name="misclassifications-function"></a><span data-ttu-id="5c853-102">Función de clasificación incorrecta</span><span class="sxs-lookup"><span data-stu-id="5c853-102">Misclassifications function</span></span>

<span data-ttu-id="5c853-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5c853-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="5c853-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c853-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c853-105">Dado un conjunto de etiquetas inferido y un conjunto de etiquetas correctas, devuelve índices en los que difiere cada conjunto de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="5c853-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="5c853-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5c853-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="5c853-107">inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5c853-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5c853-108">Las etiquetas inferidos para un conjunto de entrenamiento o de validación determinado.</span><span class="sxs-lookup"><span data-stu-id="5c853-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="5c853-109">actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5c853-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5c853-110">Las etiquetas verdaderas para un conjunto de entrenamiento o de validación determinado.</span><span class="sxs-lookup"><span data-stu-id="5c853-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="5c853-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5c853-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5c853-112">Una matriz de índices de `idx` este tipo `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="5c853-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>