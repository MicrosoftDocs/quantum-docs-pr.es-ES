---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Función de clasificación incorrecta
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 3913395fbd9f7cf96732c17ca0c726289e5087ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853923"
---
# <a name="misclassifications-function"></a>Función de clasificación incorrecta

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

## <a name="example"></a>Ejemplo

```qsharp
let misclassifications = Misclassifications([0, 1, 0, 0], [0, 1, 1, 0]);
Message($"{misclassifications}"); // Will print [2].
```