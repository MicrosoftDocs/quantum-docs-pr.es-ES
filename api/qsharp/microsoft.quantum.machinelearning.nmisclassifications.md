---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: adc7042d6108c7ec72d13340633824d3eaf5e18e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853913"
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

## <a name="example"></a>Ejemplo

```qsharp
let nMisclassifications = NMisclassifications([1, 1, 0, 0], [0, 1, 1, 0]);
Message($"{nMisclassifications}"); // Will print 2.
```