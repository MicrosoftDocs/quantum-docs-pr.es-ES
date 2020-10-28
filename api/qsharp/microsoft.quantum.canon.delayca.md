---
uid: Microsoft.Quantum.Canon.DelayCA
title: Operación DelayCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 4b4be55436d6619511a12c6fb7fbd0f23989152a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728744"
---
# <a name="delayca-operation"></a>Operación DelayCA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación determinada con un retraso.

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a>Descripción

Dada una operación y una entrada para esa operación, se aplica la operación una vez que se proporciona una entrada adicional.
En concreto, la expresión `Delay(op, arg, _)` es una operación que se aplica `op` a `arg` cuando se llama.
`Delay(op,arg,_)`La expresión permite retrasar la aplicación de `op` .

## <a name="input"></a>Entrada

### <a name="op--t--unit-ctl--adj"></a>OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> CTL + ADJ

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