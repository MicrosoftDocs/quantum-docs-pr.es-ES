---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Función de clasificación incorrecta
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211685"
---
# <a name="misclassifications-function"></a><span data-ttu-id="84b4b-102">Función de clasificación incorrecta</span><span class="sxs-lookup"><span data-stu-id="84b4b-102">Misclassifications function</span></span>

<span data-ttu-id="84b4b-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="84b4b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="84b4b-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="84b4b-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="84b4b-105">Dado un conjunto de etiquetas inferido y un conjunto de etiquetas correctas, devuelve índices en los que difiere cada conjunto de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="84b4b-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="84b4b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="84b4b-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="84b4b-107">inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="84b4b-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="84b4b-108">Las etiquetas inferidos para un conjunto de entrenamiento o de validación determinado.</span><span class="sxs-lookup"><span data-stu-id="84b4b-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="84b4b-109">actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="84b4b-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="84b4b-110">Las etiquetas verdaderas para un conjunto de entrenamiento o de validación determinado.</span><span class="sxs-lookup"><span data-stu-id="84b4b-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="84b4b-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="84b4b-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="84b4b-112">Una matriz de índices de `idx` este tipo `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="84b4b-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>