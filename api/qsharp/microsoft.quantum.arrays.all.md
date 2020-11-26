---
uid: Microsoft.Quantum.Arrays.All
title: All (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: a7c83e38c3c101b712215eb664486fe29863a52b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221698"
---
# <a name="all-function"></a>All (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz y un predicado definidos para los elementos de la matriz, y comprueba si todos los elementos de la matriz satisfacen el predicado.

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Entrada

### <a name="predicate--t---bool"></a>predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Función de `'T` a `Bool` que se usa para comprobar los elementos.


### <a name="array--t"></a>matriz: ' t []

Matriz de elementos sobre `'T` .



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

Un `Bool` valor de la función y del predicado que se aplica a todos los elementos.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de `array` elementos.

## <a name="remarks"></a>Observaciones

La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una función `predicate: 'T -> Bool` podemos generar un `Bool` valor que indica si todos los elementos cumplen `predicate` .