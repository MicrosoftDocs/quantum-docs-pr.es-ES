---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732852"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="82ad4-102">IsCoprimeI función)</span><span class="sxs-lookup"><span data-stu-id="82ad4-102">IsCoprimeI function</span></span>

<span data-ttu-id="82ad4-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="82ad4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="82ad4-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82ad4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82ad4-105">Devuelve true si $a $ y $b $ son coprimos y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="82ad4-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="82ad4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="82ad4-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="82ad4-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82ad4-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82ad4-108">el primer número de la Primality que se está probando</span><span class="sxs-lookup"><span data-stu-id="82ad4-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="82ad4-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82ad4-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82ad4-110">el segundo número de la Primality que se está probando</span><span class="sxs-lookup"><span data-stu-id="82ad4-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="82ad4-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="82ad4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="82ad4-112">True, si $a $ y $b $ son coprimos (por ejemplo, el divisor más grande es 1) y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="82ad4-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>