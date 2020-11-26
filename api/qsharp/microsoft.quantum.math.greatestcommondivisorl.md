---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 1bd18758bb2dea8a4801cbfdf258d91f81c5d9a4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195518"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="5f5c5-102">GreatestCommonDivisorL función)</span><span class="sxs-lookup"><span data-stu-id="5f5c5-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="5f5c5-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5f5c5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5f5c5-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5f5c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5f5c5-105">Calcula el máximo común divisor de $a $ y $b $.</span><span class="sxs-lookup"><span data-stu-id="5f5c5-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="5f5c5-106">El M.C. d siempre es positivo.</span><span class="sxs-lookup"><span data-stu-id="5f5c5-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="5f5c5-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="5f5c5-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="5f5c5-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5f5c5-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5f5c5-109">el primer número del divisor más común extendido que se está calculando</span><span class="sxs-lookup"><span data-stu-id="5f5c5-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="5f5c5-110">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5f5c5-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5f5c5-111">segundo número del divisor más común extendido que se está calculando</span><span class="sxs-lookup"><span data-stu-id="5f5c5-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="5f5c5-112">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5f5c5-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5f5c5-113">Máximo común divisor de $a $ y $b $</span><span class="sxs-lookup"><span data-stu-id="5f5c5-113">Greatest common divisor of $a$ and $b$</span></span>