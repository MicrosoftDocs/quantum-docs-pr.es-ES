---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e86237f39e696485a3496f1c6dd571cd516214ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857548"
---
# <a name="extendedgreatestcommondivisori-function"></a>ExtendedGreatestCommonDivisorI función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcula una tupla $ (u, v) $ de modo que $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, donde $ \operatorname{GCD} $ es $a $ el divisor común más alto de $a $ y $b $. El M.C. d siempre es positivo.

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a>Entrada

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

el primer número del divisor más común extendido que se está calculando


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

segundo número del divisor más común extendido que se está calculando



## <a name="output--intint"></a>Salida: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

Tupla $ (u, v) $ con la propiedad $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.

## <a name="references"></a>Referencias

- Esta implementación se corresponde con https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm