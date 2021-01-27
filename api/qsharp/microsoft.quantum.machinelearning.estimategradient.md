---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: Operación EstimateGradient
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 38edcb67e7dcc5d2e971fb507a792937774a702c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844397"
---
# <a name="estimategradient-operation"></a>Operación EstimateGradient

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Calcula el degradado de entrenamiento para un clasificador secuencial en un modelo determinado y para una entrada codificada determinada.

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a>Entrada

### <a name="model--sequentialmodel"></a>Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modelo secuencial cuyo degradado se va a calcular.


### <a name="encodedinput--stategenerator"></a>encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Entrada al clasificador secuencial, codificada en una operación de preparación del estado.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Número de medidas que se van a usar para calcular el degradado.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)[]

Estimación del degradado de entrenamiento en los parámetros de entrada y de modelo dados.

## <a name="remarks"></a>Observaciones

Esta operación usa una prueba de Hadamard y la técnica de cambio de parámetros conjuntamente para calcular el degradado.