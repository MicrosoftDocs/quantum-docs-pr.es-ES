---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definido por el usuario BigFraction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732765"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="a6227-102">Tipo definido por el usuario BigFraction</span><span class="sxs-lookup"><span data-stu-id="a6227-102">BigFraction user defined type</span></span>

<span data-ttu-id="a6227-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a6227-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a6227-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a6227-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a6227-105">Representa un número racional del formulario `p/q` .</span><span class="sxs-lookup"><span data-stu-id="a6227-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="a6227-106">Integer `p` es el primer elemento de la tupla y `q` es el segundo elemento de la tupla.</span><span class="sxs-lookup"><span data-stu-id="a6227-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="a6227-107">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="a6227-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="a6227-108">Numerador: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a6227-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a6227-109">Numerador de la fracción.</span><span class="sxs-lookup"><span data-stu-id="a6227-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="a6227-110">Denominador: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a6227-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a6227-111">Denominador de la fracción/</span><span class="sxs-lookup"><span data-stu-id="a6227-111">Denominator of the fraction/</span></span>