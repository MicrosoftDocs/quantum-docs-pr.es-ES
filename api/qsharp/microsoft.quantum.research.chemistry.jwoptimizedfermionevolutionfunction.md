---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: JWOptimizedFermionEvolutionFunction función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: 40a4bccc6cf74a63c354bfd628baa45768916fe2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229926"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a>JWOptimizedFermionEvolutionFunction función)

Espacio de nombres: [Microsoft. Quantum. Research. química](xref:Microsoft.Quantum.Research.Chemistry)

Paquete: [Microsoft. Quantum. Research. química](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Representa un generador dinámico como un conjunto de puertas simulables y una expansión en la base de JWOptimized.

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>Entrada

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Índice de generador que se va a representar como una evolución de la JWOptimized.


### <a name="parityqubit--qubit"></a>parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit que determina el signo de la evolución del tiempo.



## <a name="output--evolutionunitary"></a>Salida: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

`EvolutionUnitary`Que representa la evolución del tiempo por el término al que se hace referencia en ' generatorIndex.