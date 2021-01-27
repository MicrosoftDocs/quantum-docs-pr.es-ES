---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 127f2e51e19c76f4f7973bf1ac2217d4fffd72f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848366"
---
# <a name="expmodl-function"></a><span data-ttu-id="914ca-102">ExpModL función)</span><span class="sxs-lookup"><span data-stu-id="914ca-102">ExpModL function</span></span>

<span data-ttu-id="914ca-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="914ca-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="914ca-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="914ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="914ca-105">Devuelve un entero elevado a una potencia determinada con respecto a un módulo determinado.</span><span class="sxs-lookup"><span data-stu-id="914ca-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="914ca-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="914ca-106">Description</span></span>

<span data-ttu-id="914ca-107">Supongamos que expBase $x $, Power by $p $ y modulus $N $.</span><span class="sxs-lookup"><span data-stu-id="914ca-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="914ca-108">La función devuelve $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="914ca-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="914ca-109">Damos por hecho que $N $, $x $ son positivos y la potencia no es negativa.</span><span class="sxs-lookup"><span data-stu-id="914ca-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="914ca-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="914ca-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="914ca-111">expBase: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="914ca-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="914ca-112">potencia: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="914ca-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="914ca-113">módulo: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="914ca-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="914ca-114">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="914ca-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="914ca-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="914ca-115">Remarks</span></span>

<span data-ttu-id="914ca-116">Lleva tiempo proporcional al número de bits en `power` , no al `power` propio.</span><span class="sxs-lookup"><span data-stu-id="914ca-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>