---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855397"
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

## <a name="example"></a>Ejemplo

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```