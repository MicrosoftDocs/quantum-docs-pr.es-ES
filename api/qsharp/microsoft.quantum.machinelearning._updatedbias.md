---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: _UpdatedBias función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 141edf6e425a060a995bfc181aefb1bcffdb128b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196708"
---
# <a name="_updatedbias-function"></a>_UpdatedBias función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Devuelve un valor de diferencia que conduce a una puntuación de clasificación incorrecta casi mínima.

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a>Entrada

### <a name="labeledprobabilities--doubleint"></a>labeledProbabilities: ([Double](xref:microsoft.quantum.lang-ref.double),[int](xref:microsoft.quantum.lang-ref.int)) []




### <a name="bias--double"></a>bias: [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)

