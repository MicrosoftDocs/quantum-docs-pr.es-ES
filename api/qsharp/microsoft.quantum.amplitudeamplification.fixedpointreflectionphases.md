---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 2ded197801111c26d8a33f9c2363b46ca4b6c4b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845856"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases función)

Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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