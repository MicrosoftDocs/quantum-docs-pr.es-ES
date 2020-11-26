---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229161"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="f38f9-102">MultiplyGeneratorSystem función)</span><span class="sxs-lookup"><span data-stu-id="f38f9-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="f38f9-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f38f9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f38f9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f38f9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f38f9-105">Multiplica el coeficiente de todos los términos de un `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="f38f9-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="f38f9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f38f9-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="f38f9-107">multiplicador: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f38f9-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f38f9-108">Multiplicador del coeficiente.</span><span class="sxs-lookup"><span data-stu-id="f38f9-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="f38f9-109">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="f38f9-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="f38f9-110">`GeneratorSystem` que se va a multiplicar.</span><span class="sxs-lookup"><span data-stu-id="f38f9-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="f38f9-111">Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="f38f9-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="f38f9-112">`GeneratorSystem`Que representa a un sistema con coeficientes un factor `multiplier` mayor.</span><span class="sxs-lookup"><span data-stu-id="f38f9-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="f38f9-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f38f9-113">See Also</span></span>

- [<span data-ttu-id="f38f9-114">Microsoft. Quantum. Simulation. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="f38f9-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)