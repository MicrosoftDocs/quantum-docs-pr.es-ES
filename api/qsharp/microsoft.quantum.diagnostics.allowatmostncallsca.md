---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Operación AllowAtMostNCallsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853534"
---
# <a name="allowatmostncallsca-operation"></a>Operación AllowAtMostNCallsCA

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Entre una llamada a esta operación y su método contiguo, se declara que se llama a una operación determinada a lo sumo un número determinado de veces.

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="ntimes--int"></a>nTimes: [int](xref:microsoft.quantum.lang-ref.int)

Número máximo de veces que `op` se puede llamar a.


### <a name="op--tinput--toutput--is-adj--ctl"></a>OP: ' TInput => ' TOutput es ADJ + CTL

Operación cuyas llamadas se van a restringir.


### <a name="message--string"></a>Message: [cadena](xref:microsoft.quantum.lang-ref.string)

Mensaje que se va a mostrar cuando se produzca un error.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="tinput"></a>' TInput


### <a name="toutput"></a>' TOutput '



## <a name="example"></a>Ejemplo

El siguiente fragmento de código producirá un error cuando se ejecute en equipos que admiten este diagnóstico:

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a>Observaciones

Esta operación se puede reemplazar por una no operativa en destinos que no la admitan.