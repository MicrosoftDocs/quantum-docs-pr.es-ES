---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Tipo definido por el usuario EvolutionSet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 35c0b24da284a5871fd11b6d624102b853b89d19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856068"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="ab861-102">Tipo definido por el usuario EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="ab861-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="ab861-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ab861-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ab861-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab861-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab861-105">Representa un conjunto de puertas que se pueden implementar y usar fácilmente para implementar algoritmos de simulación.</span><span class="sxs-lookup"><span data-stu-id="ab861-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="ab861-106">Los elementos del conjunto se indexan mediante una  <xref:microsoft.quantum.simulation.generatorindex> , y cada conjunto se describe mediante una función de `GeneratorIndex` a  <xref:microsoft.quantum.simulation.evolutionunitary> , que son operaciones parametrizadas por un número real que representa el tiempo.</span><span class="sxs-lookup"><span data-stu-id="ab861-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

