---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Tipo definido por el usuario ReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: 743ece778239c223573a3a8536ae8059cea09d5f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191353"
---
# <a name="reflectionphases-user-defined-type"></a>Tipo definido por el usuario ReflectionPhases

Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fases para una secuencia de reflejos parciales en amplificación de amplitud.

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="aboutstart--double"></a>AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]

Una matriz de fases para la reflexión sobre el estado de inicio.
### <a name="abouttarget--double"></a>AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]

Una matriz de fases para la reflexión sobre el estado de destino.

## <a name="remarks"></a>Observaciones

Ambas matrices deben tener la misma longitud. Tenga en cuenta que, en muchos casos, la primera fase sobre el estado de inicio y la última fase sobre el estado de destino introduce un cambio de fase global y se puede establecer en $0 $.