---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: 6129d768276b5c9d96a1b1ed9cd5a6a22d28e286
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730684"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="50196-102">TimeDependentTrotterSimulationAlgorithm función)</span><span class="sxs-lookup"><span data-stu-id="50196-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="50196-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="50196-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="50196-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50196-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50196-105">`TimeDependentSimulationAlgorithm` función que utiliza una descomposición Trotter – Suzuki para aproximar un operador unitario que resuelve la ecuación de Schrodinger dependiente del tiempo.</span><span class="sxs-lookup"><span data-stu-id="50196-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="50196-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="50196-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="50196-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="50196-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="50196-108">Duración de la evolución de tiempo simulada en un solo paso de Trotter.</span><span class="sxs-lookup"><span data-stu-id="50196-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="50196-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="50196-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="50196-110">Orden de integrador de Trotter.</span><span class="sxs-lookup"><span data-stu-id="50196-110">Order of Trotter integrator.</span></span> <span data-ttu-id="50196-111">Debe ser 1 o un número par.</span><span class="sxs-lookup"><span data-stu-id="50196-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="50196-112">Salida: [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="50196-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="50196-113">Tipo `TimeDependentSimulationAlgorithm`.</span><span class="sxs-lookup"><span data-stu-id="50196-113">A `TimeDependentSimulationAlgorithm` type.</span></span>