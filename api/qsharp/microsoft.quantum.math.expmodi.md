---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228498"
---
# <a name="expmodi-function"></a><span data-ttu-id="d1dc2-102">ExpModI función)</span><span class="sxs-lookup"><span data-stu-id="d1dc2-102">ExpModI function</span></span>

<span data-ttu-id="d1dc2-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d1dc2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d1dc2-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1dc2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1dc2-105">Devuelve un entero elevado a una potencia determinada con respecto a un módulo determinado.</span><span class="sxs-lookup"><span data-stu-id="d1dc2-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="d1dc2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1dc2-106">Description</span></span>

<span data-ttu-id="d1dc2-107">Supongamos que expBase $x $, Power by $p $ y modulus $N $.</span><span class="sxs-lookup"><span data-stu-id="d1dc2-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="d1dc2-108">La función devuelve $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="d1dc2-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="d1dc2-109">Damos por hecho que $N $, $x $ son positivos y la potencia no es negativa.</span><span class="sxs-lookup"><span data-stu-id="d1dc2-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="d1dc2-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="d1dc2-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="d1dc2-111">expBase: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1dc2-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="d1dc2-112">potencia: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1dc2-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="d1dc2-113">módulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1dc2-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="d1dc2-114">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1dc2-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="d1dc2-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d1dc2-115">Remarks</span></span>

<span data-ttu-id="d1dc2-116">Lleva tiempo proporcional al número de bits en `power` , no al `power` propio.</span><span class="sxs-lookup"><span data-stu-id="d1dc2-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>