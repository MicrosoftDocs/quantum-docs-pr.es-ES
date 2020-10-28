---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Tipo definido por el usuario RotationPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731941"
---
# <a name="rotationphases-user-defined-type"></a>Tipo definido por el usuario RotationPhases

Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Configura [](https://nuget.org/packages/)


Fases para una secuencia de rotaciones de un solo qubit en amplificación de amplitud.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Observaciones

El primer parámetro es una matriz de fases para las reflexiones, expresadas como un producto de rotaciones de un solo qubit.
[ G.H. Bajo, I. L. Chuang, https://arxiv.org/abs/1707.05391 ].