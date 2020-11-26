---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227529"
---
# <a name="pnormalized-function"></a>PNormalized función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Normaliza un vector de `Double` s en la `L(p)` norma.

Es decir, dada una matriz $x $ de tipo `Double[]` , devuelve una matriz donde todos los elementos se dividen por el $p $-Norm $ \| x \| _P $.

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a>Entrada

### <a name="p--double"></a>p: [doble](xref:microsoft.quantum.lang-ref.double)

El exponente $p $ en el $p $-Norm.


### <a name="array--double"></a>matriz: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)[]

La matriz $x $ normalizada por el $p $-Norm $ \| x \| _P $.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Math. PNorm](xref:Microsoft.Quantum.Math.PNorm)