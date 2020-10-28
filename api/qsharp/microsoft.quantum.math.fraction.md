---
uid: Microsoft.Quantum.Math.Fraction
title: Tipo definido por el usuario de fracción
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733021"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="bfb03-102">Tipo definido por el usuario de fracción</span><span class="sxs-lookup"><span data-stu-id="bfb03-102">Fraction user defined type</span></span>

<span data-ttu-id="bfb03-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="bfb03-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="bfb03-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bfb03-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bfb03-105">Representa un número racional del formulario `p/q` .</span><span class="sxs-lookup"><span data-stu-id="bfb03-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="bfb03-106">Integer `p` es el primer elemento de la tupla y `q` es el segundo elemento de la tupla.</span><span class="sxs-lookup"><span data-stu-id="bfb03-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="bfb03-107">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="bfb03-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="bfb03-108">Numerador: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bfb03-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bfb03-109">Numerador de la fracción.</span><span class="sxs-lookup"><span data-stu-id="bfb03-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="bfb03-110">Denominador: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bfb03-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bfb03-111">Denominador de la fracción/</span><span class="sxs-lookup"><span data-stu-id="bfb03-111">Denominator of the fraction/</span></span>