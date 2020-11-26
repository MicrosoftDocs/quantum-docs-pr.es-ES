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
# <a name="nmisclassifications-function"></a>NMisclassifications función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dado un conjunto de etiquetas inferido y un conjunto de etiquetas correctas, devuelve el número de índices en los que difiere cada conjunto de etiquetas.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Entrada

### <a name="proposed--int"></a>propuesto: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>real: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Número de índices de `idx` este tipo `inferredLabels[idx] != actualLabels[idx]` .