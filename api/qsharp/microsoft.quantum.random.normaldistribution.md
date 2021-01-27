---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814184"
---
# <a name="normaldistribution-function"></a>NormalDistribution función)

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devuelve una distribución normal con una media y una varianza determinadas.

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Entrada

### <a name="mean--double"></a>promedio: [doble](xref:microsoft.quantum.lang-ref.double)




### <a name="variance--double"></a>varianza: [doble](xref:microsoft.quantum.lang-ref.double)





## <a name="output--continuousdistribution"></a>Salida: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>Ejemplo

En el siguiente ejemplo se dibujan 10 ejemplos de la distribución normal con la media 2 y la desviación estándar 0,1:

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. random. StandardNormalDistribution](xref:Microsoft.Quantum.Random.StandardNormalDistribution)