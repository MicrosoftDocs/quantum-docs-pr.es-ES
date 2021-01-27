---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Función muestreada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854943"
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

