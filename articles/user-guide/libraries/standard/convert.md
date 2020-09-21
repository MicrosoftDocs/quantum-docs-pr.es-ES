---
title: Conversiones de tipos en las Q# bibliotecas estándar
description: Obtenga información sobre las funciones de conversión de tipos comunes y definidas por el usuario en las Q# bibliotecas estándar.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: aa8a1ad624067906998d2735c7a95174a163ce97
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835611"
---
# <a name="type-conversions"></a>Conversiones de tipos #

Q# es un lenguaje **fuertemente tipado** .
En concreto, no se Q# convierte implícitamente entre tipos distintos. Por ejemplo, `1 + 2.0` no es una Q# expresión válida.
En su lugar, Q# proporciona una variedad de funciones de conversión de tipos para crear nuevos valores de un tipo determinado.

Por ejemplo, <xref:microsoft.quantum.core.length> tiene un tipo de salida de `Int` , por lo que su salida debe convertirse primero en un objeto `Double` antes de que se pueda utilizar como parte de una expresión de punto flotante.
Esto puede hacerse mediante la <xref:microsoft.quantum.convert.intasdouble> función:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

El <xref:microsoft.quantum.convert> espacio de nombres proporciona funciones de conversión de tipos comunes para trabajar con los tipos integrados básicos, como `Int` ,, `Double` `BigInt` , `Result` y `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

El <xref:microsoft.quantum.convert> espacio de nombres también proporciona algunas conversiones más exóticas, como `FunctionAsOperation` , que convierte funciones `'T -> 'U` en nuevas operaciones `'T => 'U` .

Por último, la Q# biblioteca estándar proporciona varios tipos definidos por el usuario como <xref:microsoft.quantum.math.complex> y <xref:microsoft.quantum.arithmetic.littleendian> .
Junto con estos tipos, la biblioteca estándar proporciona funciones como <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
