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
# <a name="misclassifications-function"></a>Función de clasificación incorrecta

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


Dado un conjunto de etiquetas inferido y un conjunto de etiquetas correctas, devuelve índices en los que difiere cada conjunto de etiquetas.

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a>Entrada

### <a name="inferredlabels--int"></a>inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]

Las etiquetas inferidos para un conjunto de entrenamiento o de validación determinado.


### <a name="actuallabels--int"></a>actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]

Las etiquetas verdaderas para un conjunto de entrenamiento o de validación determinado.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)[]

Una matriz de índices de `idx` este tipo `inferredLabels[idx] != actualLabels[idx]` .