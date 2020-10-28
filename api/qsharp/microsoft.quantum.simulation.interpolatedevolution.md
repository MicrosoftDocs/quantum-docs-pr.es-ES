---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 18026b9872f6a3344a1e5c2122f55927975ccb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726308"
---
# <a name="interpolatedevolution-function"></a><span data-ttu-id="0f4d1-102">InterpolatedEvolution función)</span><span class="sxs-lookup"><span data-stu-id="0f4d1-102">InterpolatedEvolution function</span></span>

<span data-ttu-id="0f4d1-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0f4d1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0f4d1-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f4d1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f4d1-105">Interpola entre dos generadores con una programación uniforme y devuelve una operación que aplica la evolución simulada en el generador dependiente del tiempo resultante a un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="0f4d1-105">Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.</span></span>

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="0f4d1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0f4d1-106">Input</span></span>

### <a name="interpolationtime--double"></a><span data-ttu-id="0f4d1-107">interpolationTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0f4d1-107">interpolationTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0f4d1-108">Hora a la que se realiza la interpolación.</span><span class="sxs-lookup"><span data-stu-id="0f4d1-108">Time to perform the interpolation over.</span></span>


### <a name="evolutiongeneratorstart--evolutiongenerator"></a><span data-ttu-id="0f4d1-109">evolutionGeneratorStart: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="0f4d1-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="0f4d1-110">Generador inicial para simular la evolución en.</span><span class="sxs-lookup"><span data-stu-id="0f4d1-110">Initial generator to simulate evolution under.</span></span>


### <a name="evolutiongeneratorend--evolutiongenerator"></a><span data-ttu-id="0f4d1-111">evolutionGeneratorEnd: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="0f4d1-111">evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="0f4d1-112">Generador final para simular la evolución en.</span><span class="sxs-lookup"><span data-stu-id="0f4d1-112">Final generator to simulate evolution under.</span></span>


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a><span data-ttu-id="0f4d1-113">timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="0f4d1-113">timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="0f4d1-114">Un algoritmo de simulación dependiente del tiempo que se utilizará para simular la evolución durante la programación de interpolación uniforme.</span><span class="sxs-lookup"><span data-stu-id="0f4d1-114">A time-dependent simulation algorithm that will be used to simulate evolution during the uniform interpolation schedule.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="0f4d1-115">Salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="0f4d1-115">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="0f4d1-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0f4d1-116">Remarks</span></span>

<span data-ttu-id="0f4d1-117">Si se elige el tiempo de interpolación para cumplir las condiciones de Adiabatic, esta función devuelve una operación que realiza la preparación del estado de Adiabatic para el generador dinámico final.</span><span class="sxs-lookup"><span data-stu-id="0f4d1-117">If the interpolation time is chosen to meet the adiabatic conditions, then this function returns an operation which performs adiabatic state preparation for the final dynamical generator.</span></span>