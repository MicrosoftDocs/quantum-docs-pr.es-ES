---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: Operación ApplyIfElseR
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 0d7cc9f67f9dd0c69a9256f007a3aeab3e457907
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841812"
---
# <a name="applyifelser-operation"></a>Operación ApplyIfElseR

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una de dos operaciones, dependiendo del valor de un resultado clásico.

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a>Descripción

Dado un resultado `result` , se aplica la operación `zeroOp` con `zeroInput` como entrada cuando `result` es igual a `Zero` y se aplica `oneOp(oneInput)` cuando `result == One` .

## <a name="input"></a>Entrada

### <a name="result--__invalidresult__"></a>resultado: __no <Result> válido__

El resultado de la medida que se usa para determinar si `zeroOp` `oneOp` se aplica o.


### <a name="zeroop--t--unit"></a>zeroOp: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación que se va a aplicar cuando `result == Zero` .


### <a name="zeroinput--t"></a>zeroInput: ' t

Entrada que se va a proporcionar `zeroOp` cuando `result == Zero` .


### <a name="oneop--u--unit"></a>oneOp: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación que se va a aplicar cuando `result == One` .


### <a name="oneinput--u"></a>oneInput: ' U

Entrada que se va a proporcionar `oneOp` cuando `result == One` .



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación `zeroOp` que se va a aplicar condicionalmente.
### <a name="u"></a>' U

Tipo de entrada de la operación `oneOp` que se va a aplicar condicionalmente.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. Quantum. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. Quantum. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. Quantum. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Quantum. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)