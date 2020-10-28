---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Función intercalada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730197"
---
# <a name="interleaved-function"></a>Función intercalada

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


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