---
uid: Microsoft.Quantum.Logical.Conditioned
title: Función condicionada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817299"
---
# <a name="conditioned-function"></a>Función condicionada

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve uno de dos valores, dependiendo del valor de una condición booleana.

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a>Entrada

### <a name="condition--bool"></a>condición: [bool](xref:microsoft.quantum.lang-ref.bool)

Condición usada para controlar qué entrada se devuelve.


### <a name="iftrue--t"></a>ifTrue: ' t

Valor que se va a devolver cuando `condition` sea `true` .


### <a name="iffalse--t"></a>ifFalse: ' t

Valor que se va a devolver cuando `condition` sea `false` .



## <a name="output--t"></a>Salida: ' t

`ifTrue` Si `condition` es `true` , y `ifFalse` en caso contrario.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="remarks"></a>Observaciones

A diferencia del `?|` operador, esta función no cortocircuita, de modo que ambas entradas se evalúen por completo.

Hasta un comportamiento de cortocircuito, los siguientes son equivalentes:

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```