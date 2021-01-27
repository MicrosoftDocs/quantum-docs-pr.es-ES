---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848602"
---
# <a name="fold-function"></a>Fold (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Ejemplo

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```