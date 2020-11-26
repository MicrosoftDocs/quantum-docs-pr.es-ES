---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: ffb934d06f6be06cbc35a523c90d2c54e0a51353
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210036"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Combina asignaciones y pliegues en una sola función

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Descripción

Esta función recorre en iteración la `fn` función a través de la matriz, empezando por un estado inicial `state` y devuelve todos los valores intermedios, sin incluir el estado inicial.

## <a name="input"></a>Entrada

### <a name="fn--statet---state"></a>FN: (' State, ')-> ' estado

Función que se va a doblar en la matriz.


### <a name="state--state"></a>Estado: ' estado '

Estado inicial que se va a doblar


### <a name="array--t"></a>matriz: ' t []

Matriz de valores que se van a doblar



## <a name="output--state"></a>Salida: ' estado []

Todos los Estados intermedios, incluido el estado final, pero no el estado inicial.
La longitud de la matriz de salida tiene la misma longitud que `array` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="state"></a>' Estado

El tipo de Estados en que `fn` funciona la función, es decir, acepta como primera entrada y devuelve.
### <a name="t"></a>Traslada

Tipo de `array` elementos.