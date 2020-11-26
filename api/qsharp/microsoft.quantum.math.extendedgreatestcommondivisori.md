---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 365e91e84add0d57d5a3cf203bbf23d96979b251
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195534"
---
# <a name="extendedgreatestcommondivisori-function"></a><span data-ttu-id="adda0-102">ExtendedGreatestCommonDivisorI función)</span><span class="sxs-lookup"><span data-stu-id="adda0-102">ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="adda0-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="adda0-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="adda0-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="adda0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="adda0-105">Calcula una tupla $ (u, v) $ de modo que $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, donde $ \operatorname{GCD} $ es $a $ el divisor común más alto de $a $ y $b $.</span><span class="sxs-lookup"><span data-stu-id="adda0-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="adda0-106">El M.C. d siempre es positivo.</span><span class="sxs-lookup"><span data-stu-id="adda0-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="adda0-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="adda0-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="adda0-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="adda0-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="adda0-109">el primer número del divisor más común extendido que se está calculando</span><span class="sxs-lookup"><span data-stu-id="adda0-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="adda0-110">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="adda0-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="adda0-111">segundo número del divisor más común extendido que se está calculando</span><span class="sxs-lookup"><span data-stu-id="adda0-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--intint"></a><span data-ttu-id="adda0-112">Salida: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="adda0-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="adda0-113">Tupla $ (u, v) $ con la propiedad $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.</span><span class="sxs-lookup"><span data-stu-id="adda0-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="adda0-114">Referencias</span><span class="sxs-lookup"><span data-stu-id="adda0-114">References</span></span>

- <span data-ttu-id="adda0-115">Esta implementación se corresponde con https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="adda0-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>