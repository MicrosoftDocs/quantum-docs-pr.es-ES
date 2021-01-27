---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854849"
---
# <a name="pnormalized-function"></a><span data-ttu-id="92e09-102">PNormalized función)</span><span class="sxs-lookup"><span data-stu-id="92e09-102">PNormalized function</span></span>

<span data-ttu-id="92e09-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="92e09-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="92e09-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="92e09-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="92e09-105">Normaliza un vector de `Double` s en la `L(p)` norma.</span><span class="sxs-lookup"><span data-stu-id="92e09-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="92e09-106">Es decir, dada una matriz $x $ de tipo `Double[]` , devuelve una matriz donde todos los elementos se dividen por el $p $-Norm $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="92e09-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="92e09-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="92e09-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="92e09-108">p: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="92e09-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="92e09-109">El exponente $p $ en el $p $-Norm.</span><span class="sxs-lookup"><span data-stu-id="92e09-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="92e09-110">matriz: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="92e09-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="92e09-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="92e09-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="92e09-112">La matriz $x $ normalizada por el $p $-Norm $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="92e09-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="92e09-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92e09-113">See Also</span></span>

- [<span data-ttu-id="92e09-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="92e09-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)