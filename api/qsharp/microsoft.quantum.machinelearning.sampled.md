---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Función muestreada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732317"
---
# <a name="sampled-function"></a>Función muestreada

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


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

