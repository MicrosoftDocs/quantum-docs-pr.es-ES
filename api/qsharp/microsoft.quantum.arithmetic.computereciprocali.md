---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: Operación ComputeReciprocalI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: c28027f7a2533885102a54a028bec37eb608f2b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846717"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="7ce95-102">Operación ComputeReciprocalI</span><span class="sxs-lookup"><span data-stu-id="7ce95-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="7ce95-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7ce95-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7ce95-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="7ce95-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="7ce95-105">Calcula el recíproco 1/x para un entero x sin signo x mediante la división de enteros.</span><span class="sxs-lookup"><span data-stu-id="7ce95-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="7ce95-106">El resultado, que se interpreta como un entero, será `floor(2^(2*n-1) / x)` .</span><span class="sxs-lookup"><span data-stu-id="7ce95-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7ce95-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="7ce95-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="7ce95-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7ce95-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7ce95-109">entero de n bits sin signo</span><span class="sxs-lookup"><span data-stu-id="7ce95-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="7ce95-110">resultado: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7ce95-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7ce95-111">la salida de bit 2N debe estar en $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="7ce95-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7ce95-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7ce95-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7ce95-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7ce95-113">Remarks</span></span>

<span data-ttu-id="7ce95-114">Para la entrada x = 0, la salida será todas.</span><span class="sxs-lookup"><span data-stu-id="7ce95-114">For the input x=0, the output will be all-ones.</span></span>