---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231099"
---
# <a name="integerbits-function"></a>IntegerBits función)

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve todas las posiciones en las que se establecen los bits de un entero.

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a>Entrada

### <a name="value--int"></a>valor: [int](xref:microsoft.quantum.lang-ref.int)

Un número no negativo.


### <a name="length--int"></a>longitud: [int](xref:microsoft.quantum.lang-ref.int)

Número de bits en la expansión binaria de `value` .



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)[]

Una matriz que contiene todas las posiciones de bits (a partir de 0) que son 1 en la expansión binaria de tener en cuenta `value` todos los bits hasta la posición `length - 1` .  Todas las posiciones se ordenan en la matriz por posición en un orden ascendente.