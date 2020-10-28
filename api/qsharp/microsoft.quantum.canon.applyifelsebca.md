---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: Operación ApplyIfElseBCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 0ebd086f4c8166a8d6b593200b0a3354c1420c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729567"
---
# <a name="applyifelsebca-operation"></a>Operación ApplyIfElseBCA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una de las dos operaciones de unitario, dependiendo del valor de un bit clásico.

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a>Descripción

Dado un bit `bit` , aplica la operación `trueOp` con `trueInput` como su entrada cuando `bit` es `true` y se aplica `falseOp(falseInput)` cuando `bit` es `false` .

## <a name="input"></a>Entrada

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Valor booleano que se usa para determinar `trueOp` si `falseOp` se aplica o.


### <a name="trueop--t--unit-adj--ctl"></a>trueOp: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

La operación unitario que se va a aplicar cuando `bit` es `true` .


### <a name="trueinput--t"></a>trueInput: ' t

Entrada que se va a proporcionar `trueOp` cuando `bit` sea `true` .


### <a name="falseop--u--unit-adj--ctl"></a>falseOp: ' U => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

La operación unitario que se va a aplicar cuando `bit` es `false` .


### <a name="falseinput--u"></a>falseInput: ' U

Entrada que se va a proporcionar `falseOp` cuando `bit` sea `false` .



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación `trueOp` que se va a aplicar condicionalmente.
### <a name="u"></a>' U

Tipo de entrada de la operación `falseOp` que se va a aplicar condicionalmente.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. Quantum. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. Quantum. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. Quantum. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Quantum. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)