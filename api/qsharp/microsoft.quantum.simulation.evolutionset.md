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
# <a name="evolutionset-user-defined-type"></a>Tipo definido por el usuario EvolutionSet

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa un conjunto de puertas que se pueden implementar y usar fácilmente para implementar algoritmos de simulación.

Los elementos del conjunto se indexan mediante una  <xref:microsoft.quantum.simulation.generatorindex> , y cada conjunto se describe mediante una función de `GeneratorIndex` a  <xref:microsoft.quantum.simulation.evolutionunitary> , que son operaciones parametrizadas por un número real que representa el tiempo.

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

