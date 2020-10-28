---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733061"
---
# <a name="expmodl-function"></a><span data-ttu-id="a408d-102">ExpModL función)</span><span class="sxs-lookup"><span data-stu-id="a408d-102">ExpModL function</span></span>

<span data-ttu-id="a408d-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a408d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a408d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a408d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a408d-105">Devuelve un entero elevado a una potencia determinada con respecto a un módulo determinado.</span><span class="sxs-lookup"><span data-stu-id="a408d-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="a408d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a408d-106">Description</span></span>

<span data-ttu-id="a408d-107">Supongamos que expBase $x $, Power by $p $ y modulus $N $.</span><span class="sxs-lookup"><span data-stu-id="a408d-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="a408d-108">La función devuelve $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="a408d-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="a408d-109">Damos por hecho que $N $, $x $ son positivos y la potencia no es negativa.</span><span class="sxs-lookup"><span data-stu-id="a408d-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="a408d-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="a408d-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="a408d-111">expBase: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a408d-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="a408d-112">potencia: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a408d-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="a408d-113">módulo: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a408d-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="a408d-114">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a408d-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="a408d-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a408d-115">Remarks</span></span>

<span data-ttu-id="a408d-116">Lleva tiempo proporcional al número de bits en `power` , no al `power` propio.</span><span class="sxs-lookup"><span data-stu-id="a408d-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>