---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730244"
---
# <a name="fold-function"></a>Fold (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


Recorre en iteración una función `f` a través de una matriz `array` y devuelve `f(f(f(initialState, array[0]), array[1]), ...)` .

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a>Entrada

### <a name="folder--statet---state"></a>carpeta: (' State, ')-> ' estado

Función que se va a doblar en la matriz.


### <a name="state--state"></a>Estado: ' estado '

Estado inicial de la carpeta.


### <a name="array--t"></a>matriz: ' t []

Matriz de valores que se van a plegar.



## <a name="output--state"></a>Salida: ' estado

Estado final devuelto por la carpeta después de recorrer en iteración todos los elementos de `array` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="state"></a>' Estado

El tipo de Estados `folder` en que funciona la función, es decir, acepta como primer argumento y devuelve.
### <a name="t"></a>Traslada

Tipo de `array` elementos.