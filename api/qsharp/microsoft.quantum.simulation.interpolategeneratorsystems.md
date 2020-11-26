---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: InterpolateGeneratorSystems función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: ee47637996313fe1b77c76f00b08417dac956247
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230589"
---
# <a name="interpolategeneratorsystems-function"></a>InterpolateGeneratorSystems función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve un objeto `TimeDependentGeneratorSystem` que representa la interpolación lineal entre dos `GeneratorSystem` .

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="generatorsystemstart--generatorsystem"></a>generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Inicio `GeneratorSystem` .


### <a name="generatorsystemend--generatorsystem"></a>generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Final `GeneratorSystem` .



## <a name="output--timedependentgeneratorsystem"></a>Salida: [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)

Que `TimeDependentGeneratorSystem` representa un sistema que es la suma de los sistemas de generador de entrada, con peso $ (1-s) $ on `generatorSystemStart` y Weight $s $ on `generatorSystemEnd` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Simulation. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [Microsoft. Quantum. Simulation. TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)