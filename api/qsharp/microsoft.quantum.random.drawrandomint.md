---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operación DrawRandomInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851137"
---
# <a name="drawrandomint-operation"></a>Operación DrawRandomInt

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dibuja un entero aleatorio en un intervalo inclusivo determinado.

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>Entrada

### <a name="min--int"></a>min: [int](xref:microsoft.quantum.lang-ref.int)

Entero más pequeño que se va a dibujar.


### <a name="max--int"></a>Max: [int](xref:microsoft.quantum.lang-ref.int)

Entero más grande que se va a dibujar.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Un entero en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.

## <a name="example"></a>Ejemplo

El siguiente fragmento de código de Q # revierte aleatoriamente un dado de seis lados:

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a>Observaciones

Se produce un error si `max <= min` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)