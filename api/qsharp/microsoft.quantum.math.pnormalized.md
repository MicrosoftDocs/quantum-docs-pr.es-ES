---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732237"
---
# <a name="pnormalized-function"></a>PNormalized función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Configura [](https://nuget.org/packages/)


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