---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: c94d873d7117fd2ee66226fab6d4bfc5b33bc46d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848908"
---
# <a name="bitsizel-function"></a><span data-ttu-id="70b47-102">BitSizeL función)</span><span class="sxs-lookup"><span data-stu-id="70b47-102">BitSizeL function</span></span>

<span data-ttu-id="70b47-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="70b47-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="70b47-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70b47-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70b47-105">Para un entero no negativo `a` , devuelve el número de bits necesarios para representar `a` .</span><span class="sxs-lookup"><span data-stu-id="70b47-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="70b47-106">Es decir, devuelve el menor $n $ que $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="70b47-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="70b47-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="70b47-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="70b47-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="70b47-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="70b47-109">Entero cuyo tamaño de bit se va a calcular.</span><span class="sxs-lookup"><span data-stu-id="70b47-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="70b47-110">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="70b47-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="70b47-111">Tamaño de bits de `a` .</span><span class="sxs-lookup"><span data-stu-id="70b47-111">The bit-size of `a`.</span></span>