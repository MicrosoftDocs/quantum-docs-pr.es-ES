---
uid: Microsoft.Quantum.Math.Fraction
title: Tipo definido por el usuario de fracción
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857512"
---
# <a name="fraction-user-defined-type"></a>Tipo definido por el usuario de fracción

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa un número racional del formulario `p/q` . Integer `p` es el primer elemento de la tupla y `q` es el segundo elemento de la tupla.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="numerator--int"></a>Numerador: [int](xref:microsoft.quantum.lang-ref.int)

Numerador de la fracción.
### <a name="denominator--int"></a>Denominador: [int](xref:microsoft.quantum.lang-ref.int)

Denominador de la fracción/