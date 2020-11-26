---
uid: Microsoft.Quantum.Canon.DelayC
title: Operación DelayC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7a11c3990802ff36856a90de927b38d2ede8bd9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216496"
---
# <a name="delayc-operation"></a>Operación DelayC

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación determinada con un retraso.

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit is Ctl
```


## <a name="description"></a>Descripción

Dada una operación y una entrada para esa operación, se aplica la operación una vez que se proporciona una entrada adicional.
En concreto, la expresión `Delay(op, arg, _)` es una operación que se aplica `op` a `arg` cuando se llama.
`Delay(op,arg,_)`La expresión permite retrasar la aplicación de `op` .

## <a name="input"></a>Entrada

### <a name="op--t--unit--is-ctl"></a>OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL

Operación que se va a aplicar.


### <a name="arg--t"></a>Arg: ' t

Entrada a la que se aplica la operación.


### <a name="aux--unit"></a>AUX: [unidad](xref:microsoft.quantum.lang-ref.unit)

Argumento que se usa para retrasar la aplicación de la operación mediante el uso de una aplicación parcial.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a retrasar.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)
- [Microsoft. Quantum. Canon. retrasado](xref:Microsoft.Quantum.Canon.Delayed)