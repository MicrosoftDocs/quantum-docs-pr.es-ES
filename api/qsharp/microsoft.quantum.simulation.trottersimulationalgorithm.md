---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730677"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="49f5d-102">TrotterSimulationAlgorithm función)</span><span class="sxs-lookup"><span data-stu-id="49f5d-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="49f5d-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="49f5d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="49f5d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49f5d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49f5d-105">`SimulationAlgorithm` función que utiliza una descomposición Trotter – Suzuki para aproximarse al operador de evolución de tiempo _(-iHt)_ .</span><span class="sxs-lookup"><span data-stu-id="49f5d-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_ .</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="49f5d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="49f5d-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="49f5d-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="49f5d-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="49f5d-108">Duración de la evolución de tiempo simulada en un solo paso de Trotter.</span><span class="sxs-lookup"><span data-stu-id="49f5d-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="49f5d-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="49f5d-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="49f5d-110">Orden de integrador de Trotter.</span><span class="sxs-lookup"><span data-stu-id="49f5d-110">Order of Trotter integrator.</span></span> <span data-ttu-id="49f5d-111">Debe ser 1 o un número par.</span><span class="sxs-lookup"><span data-stu-id="49f5d-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="49f5d-112">Salida: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="49f5d-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="49f5d-113">Tipo `SimulationAlgorithm`.</span><span class="sxs-lookup"><span data-stu-id="49f5d-113">A `SimulationAlgorithm` type.</span></span>