---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: fabfbff74572b3c96c701de5443e4265a0468d78
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728295"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="7edd9-102">TrotterStepSize función)</span><span class="sxs-lookup"><span data-stu-id="7edd9-102">TrotterStepSize function</span></span>

<span data-ttu-id="7edd9-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7edd9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7edd9-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7edd9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7edd9-105">Calcula el tamaño de paso de Trotter en la implementación recursiva del algoritmo de simulación de Trotter.</span><span class="sxs-lookup"><span data-stu-id="7edd9-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="7edd9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7edd9-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="7edd9-107">orden: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7edd9-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="7edd9-108">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7edd9-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="7edd9-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7edd9-109">Remarks</span></span>

<span data-ttu-id="7edd9-110">Esta operación usa una Convención de indexación diferente de la de [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="7edd9-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="7edd9-111">En concreto, `DecomposedIntoTimeStepsCA(_, 4)` se corresponde con el $p escalar _2 (\lambda) $ en Quant-pH/0508139.</span><span class="sxs-lookup"><span data-stu-id="7edd9-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>