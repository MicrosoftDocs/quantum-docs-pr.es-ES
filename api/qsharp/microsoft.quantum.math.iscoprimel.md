---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: a48f056d138499607d32b38b1fa0970745732c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851339"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="01457-102">IsCoprimeL función)</span><span class="sxs-lookup"><span data-stu-id="01457-102">IsCoprimeL function</span></span>

<span data-ttu-id="01457-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="01457-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="01457-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="01457-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="01457-105">Devuelve true si $a $ y $b $ son coprimos y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="01457-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="01457-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="01457-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="01457-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="01457-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="01457-108">el primer número de la Primality que se está probando</span><span class="sxs-lookup"><span data-stu-id="01457-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="01457-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="01457-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="01457-110">el segundo número de la Primality que se está probando</span><span class="sxs-lookup"><span data-stu-id="01457-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="01457-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="01457-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="01457-112">True, si $a $ y $b $ son coprimos (por ejemplo, el divisor más grande es 1) y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="01457-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>