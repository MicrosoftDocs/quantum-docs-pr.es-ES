---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operación DrawRandomDouble
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733212"
---
# <a name="drawrandomdouble-operation"></a>Operación DrawRandomDouble

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Configura [](https://nuget.org/packages/)


Dibuja un número real aleatorio en un intervalo inclusivo determinado.

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a>Entrada

### <a name="min--double"></a>min: [doble](xref:microsoft.quantum.lang-ref.double)

Número real más pequeño que se va a dibujar.


### <a name="max--double"></a>máx.: [doble](xref:microsoft.quantum.lang-ref.double)

Número real más grande que se va a dibujar.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)

Un número real aleatorio en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.

## <a name="remarks"></a>Observaciones

Se produce un error si `max <= min` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)