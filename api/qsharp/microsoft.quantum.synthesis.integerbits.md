---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730668"
---
# <a name="integerbits-function"></a>IntegerBits función)

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Configura [](https://nuget.org/packages/)


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