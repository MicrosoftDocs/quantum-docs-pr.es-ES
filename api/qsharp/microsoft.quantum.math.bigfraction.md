---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definido por el usuario BigFraction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732765"
---
# <a name="bigfraction-user-defined-type"></a>Tipo definido por el usuario BigFraction

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Configura [](https://nuget.org/packages/)


Representa un número racional del formulario `p/q` . Integer `p` es el primer elemento de la tupla y `q` es el segundo elemento de la tupla.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="numerator--bigint"></a>Numerador: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Numerador de la fracción.
### <a name="denominator--bigint"></a>Denominador: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Denominador de la fracción/