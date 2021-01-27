---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definido por el usuario BigFraction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846898"
---
# <a name="bigfraction-user-defined-type"></a>Tipo definido por el usuario BigFraction

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa un número racional del formulario `p/q` . Integer `p` es el primer elemento de la tupla y `q` es el segundo elemento de la tupla.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="numerator--bigint"></a>Numerador: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Numerador de la fracción.
### <a name="denominator--bigint"></a>Denominador: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Denominador de la fracción/