---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195858"
---
# <a name="bitsizei-function"></a><span data-ttu-id="129a9-102">BitSizeI función)</span><span class="sxs-lookup"><span data-stu-id="129a9-102">BitSizeI function</span></span>

<span data-ttu-id="129a9-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="129a9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="129a9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="129a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="129a9-105">Para un entero no negativo `a` , devuelve el número de bits necesarios para representar `a` .</span><span class="sxs-lookup"><span data-stu-id="129a9-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="129a9-106">Es decir, devuelve el menor $n $ que $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="129a9-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="129a9-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="129a9-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="129a9-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="129a9-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="129a9-109">Entero cuyo tamaño de bit se va a calcular.</span><span class="sxs-lookup"><span data-stu-id="129a9-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="129a9-110">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="129a9-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="129a9-111">Tamaño de bits de `a` .</span><span class="sxs-lookup"><span data-stu-id="129a9-111">The bit-size of `a`.</span></span>