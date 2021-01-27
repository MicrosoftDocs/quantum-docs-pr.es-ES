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
# <a name="type-conversions"></a><span data-ttu-id="dbbf0-103">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="dbbf0-103">Type Conversions</span></span> #

<span data-ttu-id="dbbf0-104">Q# es un lenguaje **fuertemente tipado** .</span><span class="sxs-lookup"><span data-stu-id="dbbf0-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="dbbf0-105">En concreto, no se Q# convierte implícitamente entre tipos distintos.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="dbbf0-106">Por ejemplo, `1 + 2.0` no es una Q# expresión válida.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="dbbf0-107">En su lugar, Q# proporciona una variedad de funciones de conversión de tipos para crear nuevos valores de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="dbbf0-108">Por ejemplo, <xref:Microsoft.Quantum.Core.Length> tiene un tipo de salida de `Int` , por lo que su salida debe convertirse primero en un objeto `Double` antes de que se pueda utilizar como parte de una expresión de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="dbbf0-109">Esto puede hacerse mediante la <xref:Microsoft.Quantum.Convert.IntAsDouble> función:</span><span class="sxs-lookup"><span data-stu-id="dbbf0-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="dbbf0-110">El <xref:Microsoft.Quantum.Convert> espacio de nombres proporciona funciones de conversión de tipos comunes para trabajar con los tipos integrados básicos, como `Int` ,, `Double` `BigInt` , `Result` y `Bool` :</span><span class="sxs-lookup"><span data-stu-id="dbbf0-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="dbbf0-111">El <xref:Microsoft.Quantum.Convert> espacio de nombres también proporciona algunas conversiones más exóticas, como `FunctionAsOperation` , que convierte funciones `'T -> 'U` en nuevas operaciones `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="dbbf0-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="dbbf0-112">Por último, la Q# biblioteca estándar proporciona varios tipos definidos por el usuario como <xref:Microsoft.Quantum.Math.Complex> y <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .</span><span class="sxs-lookup"><span data-stu-id="dbbf0-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="dbbf0-113">Junto con estos tipos, la biblioteca estándar proporciona funciones como <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :</span><span class="sxs-lookup"><span data-stu-id="dbbf0-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
