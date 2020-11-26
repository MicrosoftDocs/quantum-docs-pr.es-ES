---
uid: Microsoft.Quantum.Math.Fraction
title: Tipo definido por el usuario de fracción
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210682"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="ae9b2-102">Tipo definido por el usuario de fracción</span><span class="sxs-lookup"><span data-stu-id="ae9b2-102">Fraction user defined type</span></span>

<span data-ttu-id="ae9b2-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ae9b2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ae9b2-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae9b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae9b2-105">Representa un número racional del formulario `p/q` .</span><span class="sxs-lookup"><span data-stu-id="ae9b2-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="ae9b2-106">Integer `p` es el primer elemento de la tupla y `q` es el segundo elemento de la tupla.</span><span class="sxs-lookup"><span data-stu-id="ae9b2-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="ae9b2-107">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="ae9b2-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="ae9b2-108">Numerador: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ae9b2-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ae9b2-109">Numerador de la fracción.</span><span class="sxs-lookup"><span data-stu-id="ae9b2-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="ae9b2-110">Denominador: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ae9b2-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ae9b2-111">Denominador de la fracción/</span><span class="sxs-lookup"><span data-stu-id="ae9b2-111">Denominator of the fraction/</span></span>