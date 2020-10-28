---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732245"
---
# <a name="pnorm-function"></a>PNorm función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Configura [](https://nuget.org/packages/)


Devuelve la `L(p)` norma de un vector de `Double` s.

Es decir, dada una matriz $x $ de tipo `Double[]` , devuelve el $p $-Norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $.

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a>Entrada

### <a name="p--double"></a>p: [doble](xref:microsoft.quantum.lang-ref.double)

El exponente $p $ en el $p $-Norm.


### <a name="array--double"></a>matriz: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)

El $p $-norma $ \| x \| _P $.