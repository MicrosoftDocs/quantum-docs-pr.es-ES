---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Tipo definido por el usuario EvolutionSet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: ee8f3c0716f035dcb0c4fad557092fbf8dd3c356
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229416"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="a78cb-102">Tipo definido por el usuario EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="a78cb-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="a78cb-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a78cb-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a78cb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a78cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a78cb-105">Representa un conjunto de puertas que se pueden implementar y usar fácilmente para implementar algoritmos de simulación.</span><span class="sxs-lookup"><span data-stu-id="a78cb-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="a78cb-106">Los elementos del conjunto se indexan mediante una  <xref:microsoft.quantum.simulation.generatorindex> , y cada conjunto se describe mediante una función de `GeneratorIndex` a  <xref:microsoft.quantum.simulation.evolutionunitary> , que son operaciones parametrizadas por un número real que representa el tiempo.</span><span class="sxs-lookup"><span data-stu-id="a78cb-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

