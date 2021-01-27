---
uid: Microsoft.Quantum.Random.StandardNormalDistribution
title: StandardNormalDistribution función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: StandardNormalDistribution
qsharp.summary: Returns a normal distribution with mean 0 and variance 1.
ms.openlocfilehash: e1776339655c33516f7b3d156f1b377a0c74d250
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857809"
---
# <a name="standardnormaldistribution-function"></a>StandardNormalDistribution función)

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devuelve una distribución normal con una media de 0 y una varianza de 1.

```qsharp
function StandardNormalDistribution () : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="output--continuousdistribution"></a>Salida: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>Ejemplo

En el siguiente ejemplo se dibujan 10 ejemplos de la distribución normal estándar:

```qsharp
let samples = DrawMany((StandardNormalDistribution())::Sample, 10, ());
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. random. NormalDistribution](xref:Microsoft.Quantum.Random.NormalDistribution)