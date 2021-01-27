---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846238"
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

## <a name="example"></a>Ejemplo

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```