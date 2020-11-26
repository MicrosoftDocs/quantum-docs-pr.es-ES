---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Tipo definido por el usuario RotationPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191370"
---
# <a name="rotationphases-user-defined-type"></a>Tipo definido por el usuario RotationPhases

Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fases para una secuencia de rotaciones de un solo qubit en amplificación de amplitud.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Observaciones

El primer parámetro es una matriz de fases para las reflexiones, expresadas como un producto de rotaciones de un solo qubit.
[ G.H. Bajo, I. L. Chuang, https://arxiv.org/abs/1707.05391 ].