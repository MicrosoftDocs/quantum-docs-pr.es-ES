---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 212ed4c473fab3572f73ea250061057ad13e393f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725816"
---
# <a name="interpolategeneratorsystemsimpl-function"></a><span data-ttu-id="216e9-102">InterpolateGeneratorSystemsImpl función)</span><span class="sxs-lookup"><span data-stu-id="216e9-102">InterpolateGeneratorSystemsImpl function</span></span>

<span data-ttu-id="216e9-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="216e9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="216e9-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="216e9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="216e9-105">Interpola linealmente entre dos `GeneratorSystems` según un parámetro de programación `s` entre 0 y 1 (inclusive).</span><span class="sxs-lookup"><span data-stu-id="216e9-105">Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).</span></span>

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="216e9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="216e9-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="216e9-107">Programación: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="216e9-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="216e9-108">Un parámetro de programación $s \en [0, 1] $.</span><span class="sxs-lookup"><span data-stu-id="216e9-108">A schedule parameter $s\in[0,1]$.</span></span>


### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="216e9-109">generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="216e9-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="216e9-110">Inicio `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="216e9-110">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="216e9-111">generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="216e9-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="216e9-112">Final `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="216e9-112">The end `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="216e9-113">Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="216e9-113">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="216e9-114">Que `GeneratorSystem` representa un sistema que es la suma de los sistemas de generador de entrada, con peso $ (1-s) $ on `generatorSystemStart` y Weight $s $ on `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="216e9-114">A `GeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="216e9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="216e9-115">See Also</span></span>

- [<span data-ttu-id="216e9-116">Microsoft. Quantum. Simulation. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="216e9-116">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)