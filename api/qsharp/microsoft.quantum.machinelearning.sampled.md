---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Función muestreada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211634"
---
# <a name="sampled-function"></a>Función muestreada

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Muestrea una matriz determinada, usando la programación especificada.

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="schedule--samplingschedule"></a>Programación: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Una programación que se va a usar en los valores de muestreo.


### <a name="values--t"></a>valores: ' t []

Matriz de valores que se van a muestrear.



## <a name="output--t"></a>Salida: ' t []

Matriz de elementos a partir de valores, siguiendo la programación especificada.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

