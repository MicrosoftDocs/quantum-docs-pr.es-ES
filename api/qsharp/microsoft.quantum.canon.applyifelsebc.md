---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: Operación ApplyIfElseBC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 6140a8382cbd00589d1aef99e004f71f5d9295a9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841818"
---
# <a name="applyifelsebc-operation"></a>Operación ApplyIfElseBC

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una de dos operaciones controlables, dependiendo del valor de un bit clásico.

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit is Ctl
```


## <a name="description"></a>Descripción

Dado un bit `bit` , aplica la operación `trueOp` con `trueInput` como su entrada cuando `bit` es `true` y se aplica `falseOp(falseInput)` cuando `bit` es `false` .

## <a name="input"></a>Entrada

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Valor booleano que se usa para determinar `trueOp` si `falseOp` se aplica o.


### <a name="trueop--t--unit--is-ctl"></a>trueOp: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL

Operación controlable que se va a aplicar cuando `bit` es `true` .


### <a name="trueinput--t"></a>trueInput: ' t

Entrada que se va a proporcionar `trueOp` cuando `bit` sea `true` .


### <a name="falseop--u--unit--is-ctl"></a>falseOp: ' U => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL

Operación controlable que se va a aplicar cuando `bit` es `false` .


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