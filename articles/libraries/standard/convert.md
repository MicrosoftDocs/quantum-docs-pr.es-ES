---
title: 'Bibliotecas estándar de Q #: conversiones de tipo | Microsoft Docs'
description: 'Bibliotecas estándar de Q #: conversiones de tipo'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 4716f0d9562229f08ef6f0f5f80961f793de4c5c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184481"
---
# <a name="type-conversions"></a><span data-ttu-id="28b4e-103">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="28b4e-103">Type Conversions</span></span> #

<span data-ttu-id="28b4e-104">Q # es un lenguaje **fuertemente tipado** .</span><span class="sxs-lookup"><span data-stu-id="28b4e-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="28b4e-105">En concreto, Q # no se convierte implícitamente entre tipos distintos.</span><span class="sxs-lookup"><span data-stu-id="28b4e-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="28b4e-106">Por ejemplo, `1 + 2.0` no es una expresión de Q # válida.</span><span class="sxs-lookup"><span data-stu-id="28b4e-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="28b4e-107">En su lugar, Q # proporciona una variedad de funciones de conversión de tipos para construir nuevos valores de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="28b4e-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="28b4e-108">Por ejemplo, <xref:microsoft.quantum.core.length> tiene un tipo de salida de `Int`, por lo que su salida debe convertirse primero en un `Double` antes de que se pueda utilizar como parte de una expresión de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="28b4e-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="28b4e-109">Esto puede hacerse mediante la función <xref:microsoft.quantum.convert.intasdouble>:</span><span class="sxs-lookup"><span data-stu-id="28b4e-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="28b4e-110">El espacio de nombres <xref:microsoft.quantum.convert> proporciona funciones de conversión de tipos comunes para trabajar con los tipos integrados básicos, como `Int`, `Double`, `BigInt`, `Result`y `Bool`:</span><span class="sxs-lookup"><span data-stu-id="28b4e-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="28b4e-111">El espacio de nombres <xref:microsoft.quantum.convert> también proporciona algunas conversiones más exóticas, como `FunctionAsOperation`, que convierte las funciones `'T -> 'U` en nuevas operaciones `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="28b4e-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="28b4e-112">Por último, la biblioteca estándar de preguntas y respuestas proporciona una serie de tipos definidos por el usuario como <xref:microsoft.quantum.math.complex> y <xref:microsoft.quantum.arithmetic.littleendian>.</span><span class="sxs-lookup"><span data-stu-id="28b4e-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="28b4e-113">Junto con estos tipos, la biblioteca estándar proporciona funciones como <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span><span class="sxs-lookup"><span data-stu-id="28b4e-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```