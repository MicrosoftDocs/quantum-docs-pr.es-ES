---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Operación AllowAtMostNCallsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727370"
---
# <a name="allowatmostncallsca-operation"></a>Operación AllowAtMostNCallsCA

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Configura [](https://nuget.org/packages/)


Entre una llamada a esta operación y su método contiguo, se declara que se llama a una operación determinada a lo sumo un número determinado de veces.

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="ntimes--int"></a>nTimes: [int](xref:microsoft.quantum.lang-ref.int)

Número máximo de veces que `op` se puede llamar a.


### <a name="op--tinput--toutput-adj--ctl"></a>OP: ' TInput => ' TOutput ajustable + CTL

Operación cuyas llamadas se van a restringir.


### <a name="message--string"></a>Message: [cadena](xref:microsoft.quantum.lang-ref.string)

Mensaje que se va a mostrar cuando se produzca un error.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="tinput"></a>' TInput


### <a name="toutput"></a>' TOutput '



## <a name="remarks"></a>Observaciones

Esta operación se puede reemplazar por una no operativa en destinos que no la admitan.