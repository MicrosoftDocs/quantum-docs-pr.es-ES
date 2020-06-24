---
title: Conversiones de tipos en las bibliotecas estándar de preguntas y respuestas
description: Obtenga información sobre las funciones de conversión de tipos comunes y definidas por el usuario en las bibliotecas de preguntas y respuestas.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275741"
---
# <a name="type-conversions"></a>Conversiones de tipos #

Q # es un lenguaje **fuertemente tipado** .
En concreto, Q # no se convierte implícitamente entre tipos distintos. Por ejemplo, `1 + 2.0` no es una expresión de Q # válida.
En su lugar, Q # proporciona una variedad de funciones de conversión de tipos para construir nuevos valores de un tipo determinado.

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

Por último, la biblioteca estándar de preguntas y respuestas proporciona una serie de tipos definidos por el usuario como <xref:microsoft.quantum.math.complex> y <xref:microsoft.quantum.arithmetic.littleendian> .
Junto con estos tipos, la biblioteca estándar proporciona funciones como <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
