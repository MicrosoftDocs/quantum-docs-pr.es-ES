---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operación DrawRandomDouble
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847626"
---
# <a name="drawrandomdouble-operation"></a>Operación DrawRandomDouble

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>Ejemplo

El siguiente fragmento de código de Q # dibuja aleatoriamente un ángulo entre $0 $ y $2 \pi $:

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a>Observaciones

Se produce un error si `max <= min` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)