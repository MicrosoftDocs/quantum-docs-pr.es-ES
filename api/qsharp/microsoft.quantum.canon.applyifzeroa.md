---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: Operación ApplyIfZeroA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: 23c494d144ef61d40c3ca7a5de452472ffa70335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844904"
---
# <a name="applyifzeroa-operation"></a>Operación ApplyIfZeroA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación adjointable condicionada en un valor de resultado clásico a cero.

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a>Descripción

Dada una operación `op` y un valor de resultado `result` , se aplica `op` a `target` si `result` es `Zero` . Si es `One` , no sucede nada con `target` .
El sufijo `A` indica que la operación que se va a aplicar es adjointable.

## <a name="input"></a>Entrada

### <a name="result--__invalidresult__"></a>resultado: __no <Result> válido__

Resultado de la medida que controla si se aplica o no la operación.


### <a name="op--t--unit--is-adj"></a>OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ

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