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
# <a name="pnormalized-function"></a><span data-ttu-id="4f5a9-102">PNormalized función)</span><span class="sxs-lookup"><span data-stu-id="4f5a9-102">PNormalized function</span></span>

<span data-ttu-id="4f5a9-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4f5a9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4f5a9-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4f5a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4f5a9-105">Normaliza un vector de `Double` s en la `L(p)` norma.</span><span class="sxs-lookup"><span data-stu-id="4f5a9-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="4f5a9-106">Es decir, dada una matriz $x $ de tipo `Double[]` , devuelve una matriz donde todos los elementos se dividen por el $p $-Norm $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="4f5a9-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="4f5a9-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="4f5a9-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="4f5a9-108">p: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4f5a9-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4f5a9-109">El exponente $p $ en el $p $-Norm.</span><span class="sxs-lookup"><span data-stu-id="4f5a9-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="4f5a9-110">matriz: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4f5a9-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="4f5a9-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4f5a9-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4f5a9-112">La matriz $x $ normalizada por el $p $-Norm $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="4f5a9-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f5a9-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f5a9-113">See Also</span></span>

- [<span data-ttu-id="4f5a9-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="4f5a9-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)