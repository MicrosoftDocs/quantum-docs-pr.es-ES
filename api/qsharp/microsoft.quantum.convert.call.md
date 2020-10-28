---
uid: Microsoft.Quantum.Convert.Call
title: Operación de llamada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727569"
---
# <a name="call-operation"></a>Operación de llamada

Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Configura [](https://nuget.org/packages/)


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