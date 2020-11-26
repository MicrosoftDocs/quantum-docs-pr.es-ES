---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: Tipo definido por el usuario EvolutionGenerator
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: 9e0fc5a232070c238aad943ab73f064999237c15
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229450"
---
# <a name="evolutiongenerator-user-defined-type"></a>Tipo definido por el usuario EvolutionGenerator

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa un generador dinámico como un conjunto de puertas simulables y una expansión en términos de esa base.

Último parámetro para el número de términos.

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```

