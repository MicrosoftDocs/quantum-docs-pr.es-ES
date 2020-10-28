---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 77bdb040908e9a8af81dee09451a3582f7b7d159
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733013"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="65220-102">GreatestCommonDivisorL función)</span><span class="sxs-lookup"><span data-stu-id="65220-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="65220-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="65220-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="65220-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="65220-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="65220-105">Calcula el máximo común divisor de $a $ y $b $.</span><span class="sxs-lookup"><span data-stu-id="65220-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="65220-106">El M.C. d siempre es positivo.</span><span class="sxs-lookup"><span data-stu-id="65220-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="65220-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="65220-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="65220-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="65220-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="65220-109">el primer número del divisor más común extendido que se está calculando</span><span class="sxs-lookup"><span data-stu-id="65220-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="65220-110">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="65220-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="65220-111">segundo número del divisor más común extendido que se está calculando</span><span class="sxs-lookup"><span data-stu-id="65220-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="65220-112">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="65220-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="65220-113">Máximo común divisor de $a $ y $b $</span><span class="sxs-lookup"><span data-stu-id="65220-113">Greatest common divisor of $a$ and $b$</span></span>