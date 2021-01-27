---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operación ForEach
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848583"
---
# <a name="foreach-operation"></a>Operación ForEach

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz y una operación que se define para los elementos de la matriz, devuelve una nueva matriz que consta de las imágenes de la matriz original en la operación.

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Entrada

### <a name="action--t--u"></a>acción: ' t => ' U 

Una operación de `'T` a `'U` que se aplica a cada elemento.


### <a name="array--t"></a>matriz: ' t []

Matriz de elementos sobre `'T` .



## <a name="output--u"></a>Salida: ' U []

Matriz `'U[]` de elementos que se asignan mediante la `action` operación.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de `array` elementos.
### <a name="u"></a>' U

El tipo de resultado de la `action` operación.

## <a name="remarks"></a>Observaciones

La operación se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una operación, `action : 'T -> 'U` podemos asignar los elementos de la matriz y generar una nueva matriz de tipo `'U[]` .