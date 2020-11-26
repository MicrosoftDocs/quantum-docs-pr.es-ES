---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operación ComputeReciprocalFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: 3ca050d6ce9daaa10e14c2f12dd571398cf436b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223398"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="1c4d0-102">Operación ComputeReciprocalFxP</span><span class="sxs-lookup"><span data-stu-id="1c4d0-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="1c4d0-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1c4d0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1c4d0-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="1c4d0-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="1c4d0-105">Calcula $1/x $ para un número de punto fijo $x $.</span><span class="sxs-lookup"><span data-stu-id="1c4d0-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1c4d0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1c4d0-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="1c4d0-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="1c4d0-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="1c4d0-108">Número de punto fijo que se va a invertir.</span><span class="sxs-lookup"><span data-stu-id="1c4d0-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="1c4d0-109">resultado: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="1c4d0-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="1c4d0-110">Número de punto fijo que contendrá el resultado.</span><span class="sxs-lookup"><span data-stu-id="1c4d0-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="1c4d0-111">Se debe inicializar en $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="1c4d0-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c4d0-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c4d0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

