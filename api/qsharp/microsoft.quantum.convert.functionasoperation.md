---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727562"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation función)

Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Configura [](https://nuget.org/packages/)


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