---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definido por el usuario BigFraction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211090"
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