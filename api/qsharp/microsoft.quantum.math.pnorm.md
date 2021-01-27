---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 6207cca6cda5f9030facd31c327e58bdb9ecbf14
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847655"
---
# <a name="pnorm-function"></a>PNorm función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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