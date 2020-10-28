---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: Operación ApplyIfZeroC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: cfc2a659f4da011baadff1a0d6a20a2a36d0a285
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729489"
---
# <a name="applyifzeroc-operation"></a>Operación ApplyIfZeroC

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación controlable condicionada en un valor de resultado clásico a cero.

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a>Descripción

Dada una operación `op` y un valor de resultado `result` , se aplica `op` a `target` si `result` es `Zero` . Si es `One` , no sucede nada con `target` .
El sufijo `C` indica que la operación que se va a aplicar es controlable.

## <a name="input"></a>Entrada

### <a name="result--__invalidresult__"></a>resultado: __no <Result> válido__

Resultado de la medida que controla si se aplica o no la operación.


### <a name="op--t--unit-ctl"></a>OP: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)

Operación que se va a aplicar condicionalmente.


### <a name="target--t"></a>destino: ' t

Entrada a la que se aplica la operación.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar condicionalmente.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyIfZeroC](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [Microsoft. Quantum. Canon. ApplyIfZeroA](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [Microsoft. Quantum. Canon. ApplyIfZeroCA](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)