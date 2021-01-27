---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Función intercalada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848115"
---
# <a name="interleaved-function"></a>Función intercalada

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Intercala dos matrices de (casi) el mismo tamaño.

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>Descripción

Esta función devuelve el intercalado de dos matrices, comenzando por el primer elemento de la primera matriz, el primer elemento de la segunda matriz, etc.

La primera matriz debe tener la misma longitud que la segunda, o bien puede tener un elemento más.

## <a name="input"></a>Entrada

### <a name="first--t"></a>primero: ' t []

Primera matriz que se va a intercalar.


### <a name="second--t"></a>segundo: ' t []

Segunda matriz que se va a intercalar.



## <a name="output--t"></a>Salida: ' t []

Matriz intercalada

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de cada elemento de `first` y `second` .

## <a name="example"></a>Ejemplo

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```