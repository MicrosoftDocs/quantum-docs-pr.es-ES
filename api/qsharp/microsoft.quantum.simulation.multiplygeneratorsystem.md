---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 1d28de99dab3f7aca4bf3706fe98f5ef7c5286a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730925"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="b7489-102">MultiplyGeneratorSystem función)</span><span class="sxs-lookup"><span data-stu-id="b7489-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="b7489-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b7489-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b7489-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7489-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7489-105">Multiplica el coeficiente de todos los términos de un `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="b7489-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="b7489-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b7489-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="b7489-107">multiplicador: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7489-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b7489-108">Multiplicador del coeficiente.</span><span class="sxs-lookup"><span data-stu-id="b7489-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="b7489-109">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="b7489-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="b7489-110">`GeneratorSystem` que se va a multiplicar.</span><span class="sxs-lookup"><span data-stu-id="b7489-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="b7489-111">Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="b7489-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="b7489-112">`GeneratorSystem`Que representa a un sistema con coeficientes un factor `multiplier` mayor.</span><span class="sxs-lookup"><span data-stu-id="b7489-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7489-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7489-113">See Also</span></span>

- [<span data-ttu-id="b7489-114">Microsoft. Quantum. Simulation. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="b7489-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)