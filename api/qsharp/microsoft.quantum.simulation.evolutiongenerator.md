---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: Tipo definido por el usuario EvolutionGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: be741216bf99305bf5f1d149c815e98aba36aad1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726327"
---
# <a name="evolutiongenerator-user-defined-type"></a><span data-ttu-id="31a3b-102">Tipo definido por el usuario EvolutionGenerator</span><span class="sxs-lookup"><span data-stu-id="31a3b-102">EvolutionGenerator user defined type</span></span>

<span data-ttu-id="31a3b-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="31a3b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="31a3b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31a3b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31a3b-105">Representa un generador dinámico como un conjunto de puertas simulables y una expansión en términos de esa base.</span><span class="sxs-lookup"><span data-stu-id="31a3b-105">Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.</span></span>

<span data-ttu-id="31a3b-106">Último parámetro para el número de términos.</span><span class="sxs-lookup"><span data-stu-id="31a3b-106">Last parameter for number of terms.</span></span>

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```

