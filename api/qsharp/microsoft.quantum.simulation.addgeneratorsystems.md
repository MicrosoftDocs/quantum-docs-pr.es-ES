---
uid: Microsoft.Quantum.Simulation.AddGeneratorSystems
title: AddGeneratorSystems función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: b23fc89b941a7cdd93ee7938dda50eb14e3ed528
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857936"
---
# <a name="addgeneratorsystems-function"></a>AddGeneratorSystems función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Agrega dos `GeneratorSystem` para crear un nuevo `GeneratorSystem` .

```qsharp
function AddGeneratorSystems (generatorSystemA : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemB : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="generatorsystema--generatorsystem"></a>generatorSystemA: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Primer objeto `GeneratorSystem`.


### <a name="generatorsystemb--generatorsystem"></a>generatorSystemB: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Segundo objeto `GeneratorSystem`.



## <a name="output--generatorsystem"></a>Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Que `GeneratorSystem` representa un sistema que es la suma de los sistemas de generador de entrada.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Simulation. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)