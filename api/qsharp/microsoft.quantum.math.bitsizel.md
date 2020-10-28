---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 97068f12050317a9aa17c95f33650ef6f406066d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732756"
---
# <a name="bitsizel-function"></a><span data-ttu-id="6ad2f-102">BitSizeL función)</span><span class="sxs-lookup"><span data-stu-id="6ad2f-102">BitSizeL function</span></span>

<span data-ttu-id="6ad2f-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6ad2f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6ad2f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ad2f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ad2f-105">Para un entero no negativo `a` , devuelve el número de bits necesarios para representar `a` .</span><span class="sxs-lookup"><span data-stu-id="6ad2f-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="6ad2f-106">Es decir, devuelve el menor $n $ que $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="6ad2f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="6ad2f-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="6ad2f-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6ad2f-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6ad2f-109">Entero cuyo tamaño de bit se va a calcular.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="6ad2f-110">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ad2f-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ad2f-111">Tamaño de bits de `a` .</span><span class="sxs-lookup"><span data-stu-id="6ad2f-111">The bit-size of `a`.</span></span>