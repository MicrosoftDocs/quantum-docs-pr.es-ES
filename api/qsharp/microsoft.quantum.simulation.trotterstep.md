---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733989"
---
# <a name="trotterstep-function"></a><span data-ttu-id="4269f-102">TrotterStep función)</span><span class="sxs-lookup"><span data-stu-id="4269f-102">TrotterStep function</span></span>

<span data-ttu-id="4269f-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4269f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4269f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4269f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4269f-105">Implementa un único paso temporal de la evolución del tiempo por parte del sistema descrito en un `EvolutionGenerator` mediante una descomposición Trotter – Suzuki.</span><span class="sxs-lookup"><span data-stu-id="4269f-105">Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.</span></span>

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="4269f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4269f-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="4269f-107">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="4269f-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="4269f-108">Una descripción completa del sistema que se va a simular.</span><span class="sxs-lookup"><span data-stu-id="4269f-108">A complete description of the system to be simulated.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="4269f-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4269f-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4269f-110">Orden de integrador de Trotter.</span><span class="sxs-lookup"><span data-stu-id="4269f-110">Order of Trotter integrator.</span></span> <span data-ttu-id="4269f-111">Debe ser 1 o un número par.</span><span class="sxs-lookup"><span data-stu-id="4269f-111">This must be either 1 or an even number.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="4269f-112">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4269f-112">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4269f-113">Duración de la evolución de tiempo simulada en un solo paso de Trotter.</span><span class="sxs-lookup"><span data-stu-id="4269f-113">Duration of simulated time-evolution in single Trotter step.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="4269f-114">Salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="4269f-114">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="4269f-115">Operación unitario que se aproxima a un solo paso de tiempo-evolución de la duración `trotterStepSize` .</span><span class="sxs-lookup"><span data-stu-id="4269f-115">Unitary operation that approximates a single step of time-evolution for duration `trotterStepSize`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4269f-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4269f-116">Remarks</span></span>

<span data-ttu-id="4269f-117">Para obtener más información sobre la descomposición Trotter – Suzuki, vea [composición ordenada por tiempo](/quantum/libraries/control-flow#time-ordered-composition).</span><span class="sxs-lookup"><span data-stu-id="4269f-117">For more on the Trotter–Suzuki decomposition, see [Time-Ordered Composition](/quantum/libraries/control-flow#time-ordered-composition).</span></span>