---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: c78e995801f67822cf98104a7319093d853b6afe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228141"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="88b74-102">IsCoprimeL función)</span><span class="sxs-lookup"><span data-stu-id="88b74-102">IsCoprimeL function</span></span>

<span data-ttu-id="88b74-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="88b74-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="88b74-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88b74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88b74-105">Devuelve true si $a $ y $b $ son coprimos y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="88b74-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="88b74-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="88b74-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="88b74-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="88b74-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="88b74-108">el primer número de la Primality que se está probando</span><span class="sxs-lookup"><span data-stu-id="88b74-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="88b74-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="88b74-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="88b74-110">el segundo número de la Primality que se está probando</span><span class="sxs-lookup"><span data-stu-id="88b74-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="88b74-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="88b74-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="88b74-112">True, si $a $ y $b $ son coprimos (por ejemplo, el divisor más grande es 1) y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="88b74-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>