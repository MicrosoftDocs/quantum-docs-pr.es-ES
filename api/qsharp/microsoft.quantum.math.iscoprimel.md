---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732252"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="6b538-102">IsCoprimeL función)</span><span class="sxs-lookup"><span data-stu-id="6b538-102">IsCoprimeL function</span></span>

<span data-ttu-id="6b538-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6b538-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6b538-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6b538-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6b538-105">Devuelve true si $a $ y $b $ son coprimos y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="6b538-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="6b538-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6b538-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="6b538-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6b538-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6b538-108">el primer número de la Primality que se está probando</span><span class="sxs-lookup"><span data-stu-id="6b538-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="6b538-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6b538-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6b538-110">el segundo número de la Primality que se está probando</span><span class="sxs-lookup"><span data-stu-id="6b538-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="6b538-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6b538-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6b538-112">True, si $a $ y $b $ son coprimos (por ejemplo, el divisor más grande es 1) y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="6b538-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>