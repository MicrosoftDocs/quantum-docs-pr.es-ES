---
uid: Microsoft.Quantum.Preparation._ApproximatelyUnprepareArbitraryStatePlan
title: _ApproximatelyUnprepareArbitraryStatePlan función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: _ApproximatelyUnprepareArbitraryStatePlan
qsharp.summary: Implementation step of arbitrary state preparation procedure.
ms.openlocfilehash: 4050a65b0830da4c3d73e84942780aa7c2643c76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733333"
---
# <a name="_approximatelyunpreparearbitrarystateplan-function"></a><span data-ttu-id="6c374-102">_ApproximatelyUnprepareArbitraryStatePlan función)</span><span class="sxs-lookup"><span data-stu-id="6c374-102">_ApproximatelyUnprepareArbitraryStatePlan function</span></span>

<span data-ttu-id="6c374-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="6c374-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="6c374-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c374-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6c374-105">Paso de implementación del procedimiento de preparación de estado arbitrario.</span><span class="sxs-lookup"><span data-stu-id="6c374-105">Implementation step of arbitrary state preparation procedure.</span></span>

```qsharp
function _ApproximatelyUnprepareArbitraryStatePlan (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], (rngControl : Range, idxTarget : Int)) : (Qubit[] => Unit is Adj + Ctl)[]
```


## <a name="input"></a><span data-ttu-id="6c374-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6c374-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="6c374-107">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6c374-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="coefficients--complexpolar"></a><span data-ttu-id="6c374-108">coeficientes: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="6c374-108">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>




### <a name="rngcontrol--range"></a><span data-ttu-id="6c374-109">rngControl: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="6c374-109">rngControl : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>




### <a name="idxtarget--int"></a><span data-ttu-id="6c374-110">idxTarget: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6c374-110">idxTarget : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="6c374-111">Salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL []</span><span class="sxs-lookup"><span data-stu-id="6c374-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>



## <a name="see-also"></a><span data-ttu-id="6c374-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c374-112">See Also</span></span>

- [<span data-ttu-id="6c374-113">Microsoft. Quantum. preparación. PrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="6c374-113">Microsoft.Quantum.Preparation.PrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareArbitraryState)
- [<span data-ttu-id="6c374-114">Microsoft. Quantum. Canon. MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="6c374-114">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)