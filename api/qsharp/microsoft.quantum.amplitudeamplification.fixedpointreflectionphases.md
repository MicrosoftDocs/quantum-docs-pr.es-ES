---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731996"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases función)

Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Configura [](https://nuget.org/packages/)


Calcula las fases de reflexión parcial para la amplificación de amplitud de punto fijo.

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Entrada

### <a name="nqueries--int"></a>nQueries: [int](xref:microsoft.quantum.lang-ref.int)

Número de consultas a la preparación de estado de Oracle. Debe ser un entero impar.


### <a name="successmin--double"></a>successMin: [Double](xref:microsoft.quantum.lang-ref.double)

Probabilidad de éxito mínima de destino.



## <a name="output--reflectionphases"></a>Salida: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Matriz de fases que se puede usar en la implementación del algoritmo Quantum de amplificación de amplitud de punto fijo.

## <a name="references"></a>Referencias

Usamos las fases de la amplificación de amplitud de puntos fijos con un número óptimo de consultas.

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Vea también "metodología de las puertas de Quantum compuestas"
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) para las fases en el `RotationPhases` formato.