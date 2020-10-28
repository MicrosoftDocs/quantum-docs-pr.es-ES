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
# <a name="pnorm-function"></a><span data-ttu-id="63adb-102">PNorm función)</span><span class="sxs-lookup"><span data-stu-id="63adb-102">PNorm function</span></span>

<span data-ttu-id="63adb-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="63adb-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="63adb-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63adb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63adb-105">Devuelve la `L(p)` norma de un vector de `Double` s.</span><span class="sxs-lookup"><span data-stu-id="63adb-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="63adb-106">Es decir, dada una matriz $x $ de tipo `Double[]` , devuelve el $p $-Norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $.</span><span class="sxs-lookup"><span data-stu-id="63adb-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="63adb-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="63adb-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="63adb-108">p: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="63adb-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="63adb-109">El exponente $p $ en el $p $-Norm.</span><span class="sxs-lookup"><span data-stu-id="63adb-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="63adb-110">matriz: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="63adb-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="63adb-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="63adb-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="63adb-112">El $p $-norma $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="63adb-112">The $p$-norm $\|x\|_p$.</span></span>