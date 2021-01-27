---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 2c110f9abf18ee81bd72a68601d5c41ff756290a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851364"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="96080-102">IsCoprimeI función)</span><span class="sxs-lookup"><span data-stu-id="96080-102">IsCoprimeI function</span></span>

<span data-ttu-id="96080-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="96080-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="96080-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="96080-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="96080-105">Devuelve true si $a $ y $b $ son coprimos y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="96080-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="96080-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="96080-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="96080-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96080-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96080-108">el primer número de la Primality que se está probando</span><span class="sxs-lookup"><span data-stu-id="96080-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="96080-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96080-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96080-110">el segundo número de la Primality que se está probando</span><span class="sxs-lookup"><span data-stu-id="96080-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="96080-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="96080-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="96080-112">True, si $a $ y $b $ son coprimos (por ejemplo, el divisor más grande es 1) y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="96080-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>