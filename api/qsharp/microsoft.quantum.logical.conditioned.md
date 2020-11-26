---
uid: Microsoft.Quantum.Logical.Conditioned
title: Función condicionada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198493"
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

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```