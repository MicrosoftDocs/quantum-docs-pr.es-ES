---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 4d2e04513c96c6e5f41e85f1df685e91e2973098
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858088"
---
# <a name="interpolatedevolution-function"></a>InterpolatedEvolution función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Interpola entre dos generadores con una programación uniforme y devuelve una operación que aplica la evolución simulada en el generador dependiente del tiempo resultante a un registro qubit.

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="interpolationtime--double"></a>interpolationTime: [Double](xref:microsoft.quantum.lang-ref.double)

Hora a la que se realiza la interpolación.


### <a name="evolutiongeneratorstart--evolutiongenerator"></a>evolutionGeneratorStart: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Generador inicial para simular la evolución en.


### <a name="evolutiongeneratorend--evolutiongenerator"></a>evolutionGeneratorEnd: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Generador final para simular la evolución en.


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a>timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

Un algoritmo de simulación dependiente del tiempo que se utilizará para simular la evolución durante la programación de interpolación uniforme.



## <a name="output--qubit--unit--is-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL



## <a name="remarks"></a>Observaciones

Si se elige el tiempo de interpolación para cumplir las condiciones de Adiabatic, esta función devuelve una operación que realiza la preparación del estado de Adiabatic para el generador dinámico final.