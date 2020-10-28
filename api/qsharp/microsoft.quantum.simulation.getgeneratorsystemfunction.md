---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 60ebbdbd1020d41a54426377043fc0c84ceec504
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733533"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="bc2ad-102">GetGeneratorSystemFunction función)</span><span class="sxs-lookup"><span data-stu-id="bc2ad-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="bc2ad-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bc2ad-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bc2ad-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc2ad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc2ad-105">Recupera la `GeneratorIndex` función en un `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="bc2ad-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="bc2ad-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bc2ad-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="bc2ad-107">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="bc2ad-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="bc2ad-108">`GeneratorSystem` de interés.</span><span class="sxs-lookup"><span data-stu-id="bc2ad-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="bc2ad-109">Salida: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="bc2ad-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="bc2ad-110">Función que indexa cada `GeneratorIndex` término en un Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="bc2ad-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc2ad-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc2ad-111">See Also</span></span>

- [<span data-ttu-id="bc2ad-112">Microsoft. Quantum. Simulation. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="bc2ad-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="bc2ad-113">Microsoft. Quantum. Simulation. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="bc2ad-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)