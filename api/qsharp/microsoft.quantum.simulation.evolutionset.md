---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Tipo definido por el usuario EvolutionSet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 41504837b281b1021a2d09ef75acc10315b4fd07
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726320"
---
# <a name="evolutionset-user-defined-type"></a>Tipo definido por el usuario EvolutionSet

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Configura [](https://nuget.org/packages/)


Representa un conjunto de puertas que se pueden implementar y usar fácilmente para implementar algoritmos de simulación.

Los elementos del conjunto se indexan mediante una  <xref:microsoft.quantum.simulation.generatorindex> , y cada conjunto se describe mediante una función de `GeneratorIndex` a  <xref:microsoft.quantum.simulation.evolutionunitary> , que son operaciones parametrizadas por un número real que representa el tiempo.

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

