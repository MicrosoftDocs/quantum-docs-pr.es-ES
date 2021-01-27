---
title: Conversiones de tipos en las Q# bibliotecas estándar
description: Obtenga información sobre las funciones de conversión de tipos comunes y definidas por el usuario en las Q# bibliotecas estándar.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: 67f47339363a52097f342c8ae4e43a8a93d606a8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858019"
---
# <a name="type-conversions"></a>Conversiones de tipos #

Q# es un lenguaje **fuertemente tipado** .
En concreto, no se Q# convierte implícitamente entre tipos distintos. Por ejemplo, `1 + 2.0` no es una Q# expresión válida.
En su lugar, Q# proporciona una variedad de funciones de conversión de tipos para crear nuevos valores de un tipo determinado.

Por ejemplo, <xref:Microsoft.Quantum.Core.Length> tiene un tipo de salida de `Int` , por lo que su salida debe convertirse primero en un objeto `Double` antes de que se pueda utilizar como parte de una expresión de punto flotante.
Esto puede hacerse mediante la <xref:Microsoft.Quantum.Convert.IntAsDouble> función:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

El <xref:Microsoft.Quantum.Convert> espacio de nombres proporciona funciones de conversión de tipos comunes para trabajar con los tipos integrados básicos, como `Int` ,, `Double` `BigInt` , `Result` y `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

El <xref:Microsoft.Quantum.Convert> espacio de nombres también proporciona algunas conversiones más exóticas, como `FunctionAsOperation` , que convierte funciones `'T -> 'U` en nuevas operaciones `'T => 'U` .

Por último, la Q# biblioteca estándar proporciona varios tipos definidos por el usuario como <xref:Microsoft.Quantum.Math.Complex> y <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .
Junto con estos tipos, la biblioteca estándar proporciona funciones como <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
