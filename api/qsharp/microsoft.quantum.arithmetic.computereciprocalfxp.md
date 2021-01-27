---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operación ComputeReciprocalFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843257"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="4b1c8-102">Operación ComputeReciprocalFxP</span><span class="sxs-lookup"><span data-stu-id="4b1c8-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="4b1c8-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4b1c8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4b1c8-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4b1c8-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4b1c8-105">Calcula $1/x $ para un número de punto fijo $x $.</span><span class="sxs-lookup"><span data-stu-id="4b1c8-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4b1c8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4b1c8-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="4b1c8-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4b1c8-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4b1c8-108">Número de punto fijo que se va a invertir.</span><span class="sxs-lookup"><span data-stu-id="4b1c8-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="4b1c8-109">resultado: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4b1c8-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4b1c8-110">Número de punto fijo que contendrá el resultado.</span><span class="sxs-lookup"><span data-stu-id="4b1c8-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="4b1c8-111">Se debe inicializar en $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="4b1c8-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b1c8-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b1c8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

