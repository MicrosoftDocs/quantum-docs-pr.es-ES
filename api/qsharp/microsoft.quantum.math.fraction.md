---
uid: Microsoft.Quantum.Math.Fraction
title: Tipo definido por el usuario de fracción
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733021"
---
# <a name="fraction-user-defined-type"></a>Tipo definido por el usuario de fracción

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Configura [](https://nuget.org/packages/)


Representa un número racional del formulario `p/q` . Integer `p` es el primer elemento de la tupla y `q` es el segundo elemento de la tupla.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="numerator--int"></a>Numerador: [int](xref:microsoft.quantum.lang-ref.int)

Numerador de la fracción.
### <a name="denominator--int"></a>Denominador: [int](xref:microsoft.quantum.lang-ref.int)

Denominador de la fracción/