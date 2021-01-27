---
uid: Microsoft.Quantum.Convert.Call
title: Operación de llamada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850211"
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