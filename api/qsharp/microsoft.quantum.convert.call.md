---
uid: Microsoft.Quantum.Convert.Call
title: Operación de llamada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214218"
---
# <a name="call-operation"></a>Operación de llamada

Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Llama a una función con una entrada determinada.

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>Descripción

Dada una función y una entrada para esa función, llama a la función y devuelve su resultado.

## <a name="input"></a>Entrada

### <a name="fn--input---output"></a>FN: salida de "entrada->"

Función a la que se va a llamar.


### <a name="input--input"></a>entrada: ' entrada

Entrada que se va a pasar a la función.



## <a name="output--output"></a>Salida: ' Output

Resultado de llamar a `fn`.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="input"></a>' Entrada


### <a name="output"></a>' Output



## <a name="remarks"></a>Observaciones

Esta operación es especialmente útil para forzar que se llame a una función en un lugar específico dentro de una operación, o para llamar a una función en la que se espera una operación.