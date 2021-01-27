---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 0f545f7888f5a9a353cc6000a12988648ac82dd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856368"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="51fdb-102">GreatestCommonDivisorL función)</span><span class="sxs-lookup"><span data-stu-id="51fdb-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="51fdb-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="51fdb-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="51fdb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="51fdb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="51fdb-105">Calcula el máximo común divisor de $a $ y $b $.</span><span class="sxs-lookup"><span data-stu-id="51fdb-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="51fdb-106">El M.C. d siempre es positivo.</span><span class="sxs-lookup"><span data-stu-id="51fdb-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="51fdb-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="51fdb-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="51fdb-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="51fdb-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="51fdb-109">el primer número del divisor más común extendido que se está calculando</span><span class="sxs-lookup"><span data-stu-id="51fdb-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="51fdb-110">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="51fdb-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="51fdb-111">segundo número del divisor más común extendido que se está calculando</span><span class="sxs-lookup"><span data-stu-id="51fdb-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="51fdb-112">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="51fdb-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="51fdb-113">Máximo común divisor de $a $ y $b $</span><span class="sxs-lookup"><span data-stu-id="51fdb-113">Greatest common divisor of $a$ and $b$</span></span>