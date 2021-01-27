---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Tipo definido por el usuario GeneratorIndex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 762dac81ea0963443f0338cea1b879856c84b0ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858382"
---
# <a name="generatorindex-user-defined-type"></a>Tipo definido por el usuario GeneratorIndex

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa un término primitivo único en el conjunto de todos los generadores dinámicos, por ejemplo, los operadores Hermitian, para los que existe una asignación de ese generador a la evolución de tiempo de ese generador, a través de `EvolutionSet` .

El primer elemento (int [], double []) es un índice que tiene un único término; por ejemplo, la cadena Pauli XXY con coeficiente 0,5 sería indexada por ([1, 1, 2], [0,5]). Como alternativa, Hamiltonians parametrizado mediante una variable continua, como X cos φ + Y sin φ, podría representarse por instancia ([], [φ]). El segundo elemento indiza el subsistema en el que actúa el generador.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a>Ejemplo

Con  <xref:microsoft.quantum.simulation.paulievolutionset> , el operador $ \pi X_2 X_5 Y_9 $ se representa como:

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a>Observaciones

> [!WARNING]
> No se define la interpretación de un, `GeneratorIndex` excepto con referencia a un conjunto determinado de generadores.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Simulation. EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft. Quantum. Simulation. PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)