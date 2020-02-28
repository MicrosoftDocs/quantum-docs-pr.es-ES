---
title: Conversiones de tipos en las bibliotecas estándar de preguntas y respuestas
description: Obtenga información sobre las funciones de conversión de tipos comunes y definidas por el usuario en las bibliotecas de preguntas y respuestas.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907807"
---
# <a name="type-conversions"></a>Conversiones de tipos #

Q # es un lenguaje **fuertemente tipado** .
En concreto, Q # no se convierte implícitamente entre tipos distintos. Por ejemplo, `1 + 2.0` no es una expresión de Q # válida.
En su lugar, Q # proporciona una variedad de funciones de conversión de tipos para construir nuevos valores de un tipo determinado.

Por ejemplo, <xref:microsoft.quantum.core.length> tiene un tipo de salida de `Int`, por lo que su salida debe convertirse primero en un `Double` antes de que se pueda utilizar como parte de una expresión de punto flotante.
Esto puede hacerse mediante la función <xref:microsoft.quantum.convert.intasdouble>:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

El espacio de nombres <xref:microsoft.quantum.convert> proporciona funciones de conversión de tipos comunes para trabajar con los tipos integrados básicos, como `Int`, `Double`, `BigInt`, `Result`y `Bool`:

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

El espacio de nombres <xref:microsoft.quantum.convert> también proporciona algunas conversiones más exóticas, como `FunctionAsOperation`, que convierte las funciones `'T -> 'U` en nuevas operaciones `'T => 'U`.

Por último, la biblioteca estándar de preguntas y respuestas proporciona una serie de tipos definidos por el usuario como <xref:microsoft.quantum.math.complex> y <xref:microsoft.quantum.arithmetic.littleendian>.
Junto con estos tipos, la biblioteca estándar proporciona funciones como <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
