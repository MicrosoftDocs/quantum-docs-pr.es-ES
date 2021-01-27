---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833841"
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