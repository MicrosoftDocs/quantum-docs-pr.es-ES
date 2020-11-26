---
uid: Microsoft.Quantum.Arrays.Any
title: Cualquier función
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: 717ab9ebcbb864a6faf1c14cd36125e589849f2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221664"
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

## <a name="remarks"></a>Observaciones

La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una función, `predicate: 'T -> Bool` podemos generar un `Bool` valor que indica si algún elemento satisface `predicate` .