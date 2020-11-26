---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194736"
---
# <a name="pnorm-function"></a><span data-ttu-id="84af3-102">PNorm función)</span><span class="sxs-lookup"><span data-stu-id="84af3-102">PNorm function</span></span>

<span data-ttu-id="84af3-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="84af3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="84af3-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84af3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84af3-105">Devuelve la `L(p)` norma de un vector de `Double` s.</span><span class="sxs-lookup"><span data-stu-id="84af3-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="84af3-106">Es decir, dada una matriz $x $ de tipo `Double[]` , devuelve el $p $-Norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $.</span><span class="sxs-lookup"><span data-stu-id="84af3-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="84af3-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="84af3-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="84af3-108">p: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="84af3-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="84af3-109">El exponente $p $ en el $p $-Norm.</span><span class="sxs-lookup"><span data-stu-id="84af3-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="84af3-110">matriz: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="84af3-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="84af3-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="84af3-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="84af3-112">El $p $-norma $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="84af3-112">The $p$-norm $\|x\|_p$.</span></span>