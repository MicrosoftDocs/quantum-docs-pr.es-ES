---
uid: Microsoft.Quantum.Arrays.Any
title: Cualquier función
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: a05f9531168bf2b32977665d38cc00f3c8e64879
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846278"
---
# <a name="any-function"></a>Cualquier función

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz y un predicado definidos para los elementos de la matriz, comprueba si al menos un elemento de la matriz satisface el predicado.

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Entrada

### <a name="predicate--t---bool"></a>predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Función de `'T` a `Bool` que se usa para comprobar los elementos.


### <a name="array--t"></a>matriz: ' t []

Matriz de elementos sobre `'T` .



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

Un `Bool` valor de la función o del predicado que se aplica a todos los elementos.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de `array` elementos.

## <a name="example"></a>Ejemplo

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function IsThreePresent() : Bool {
    let arrayOfInts = [1, 2, 3, 4, 5];
    let is3Present = IsNumberPresentInArray(3, arrayOfInts);
    return is3Present;
}

function IsNumberPresentInArray(n : Int, array : Int[]) : Bool {
    return Any(EqualI(_, n), array);
}
```

## <a name="remarks"></a>Observaciones

La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una función, `predicate: 'T -> Bool` podemos generar un `Bool` valor que indica si algún elemento satisface `predicate` .