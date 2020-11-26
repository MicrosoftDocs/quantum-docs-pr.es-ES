---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 53131a755571ad1ac0a8a984bf229b16f67dbe51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195365"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="073e7-102">IsCoprimeI función)</span><span class="sxs-lookup"><span data-stu-id="073e7-102">IsCoprimeI function</span></span>

<span data-ttu-id="073e7-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="073e7-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="073e7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="073e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="073e7-105">Devuelve true si $a $ y $b $ son coprimos y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="073e7-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="073e7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="073e7-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="073e7-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="073e7-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="073e7-108">el primer número de la Primality que se está probando</span><span class="sxs-lookup"><span data-stu-id="073e7-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="073e7-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="073e7-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="073e7-110">el segundo número de la Primality que se está probando</span><span class="sxs-lookup"><span data-stu-id="073e7-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="073e7-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="073e7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="073e7-112">True, si $a $ y $b $ son coprimos (por ejemplo, el divisor más grande es 1) y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="073e7-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>