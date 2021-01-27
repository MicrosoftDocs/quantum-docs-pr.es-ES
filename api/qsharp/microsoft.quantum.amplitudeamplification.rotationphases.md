---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Tipo definido por el usuario RotationPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843960"
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