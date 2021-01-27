---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operación DrawRandomBool
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853686"
---
# <a name="drawrandombool-operation"></a>Operación DrawRandomBool

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dada una probabilidad de éxito, devuelve una prueba de Bernoulli única que es verdadera con la probabilidad dada.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Entrada

### <a name="successprobability--double"></a>successProbability: [Double](xref:microsoft.quantum.lang-ref.double)

La probabilidad con la que `true` se debe devolver.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` con probabilidad `successProbability` y `false` con probabilidad `1.0 - successProbability` .

## <a name="example"></a>Ejemplo

Los siguientes ejemplos de fragmentos de código de Q # se voltean de una moneda sesgada:

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```