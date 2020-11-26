---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 6c1917d6f1ee69cb29fed1ab173106af1e206533
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216632"
---
# <a name="curriedop-function"></a>CurriedOp función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve una versión currificada de una operación con dos entradas.

Es decir, dada una operación con dos entradas, esta función aplica isomorphism de la $f (x, y) \equiv f (x) $ para devolver una operación de una entrada que devuelve una operación de una entrada.

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a>Entrada

### <a name="op--tu--unit"></a>OP: (' t, ' U) = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación cuya entrada es un par.



## <a name="output--t---u--unit"></a>Salida: ' t-> ' U = [unidad](xref:microsoft.quantum.lang-ref.unit) de> 

Una operación que acepta el primer elemento de un par y devuelve una operación que acepta como entrada el segundo elemento de la entrada de la operación original.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo del primer componente de una función definida en pares.
### <a name="u"></a>' U

Tipo del segundo componente de una función definida en pares.

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```