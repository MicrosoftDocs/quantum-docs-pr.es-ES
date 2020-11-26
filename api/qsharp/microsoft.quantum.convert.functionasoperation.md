---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224384"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation función)

Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Convierte funciones en operaciones.

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>Descripción

Dada una función, devuelve una operación que llama a esa función y que no hace nada más.

## <a name="input"></a>Entrada

### <a name="fn--input---output"></a>FN: salida de "entrada->"

Función que se va a convertir en una operación.



## <a name="output--input--output"></a>Salida: salida ' input => ' 

Operación `op` tal que `op(input)` es idéntica a `fn(input)` para todos los `input` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="input"></a>' Entrada

Tipo de entrada de la función que se va a convertir.
### <a name="output"></a>' Output

Tipo de salida de la función que se va a convertir.

## <a name="remarks"></a>Observaciones

Esto es especialmente útil para pasar funciones a funciones u operaciones que esperan una operación como entrada.