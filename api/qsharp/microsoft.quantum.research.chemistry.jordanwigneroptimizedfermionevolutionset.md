---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: JordanWignerOptimizedFermionEvolutionSet función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 941d66a936ef1a2ac76230d14ca8437ac2a4a049
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857883"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a>JordanWignerOptimizedFermionEvolutionSet función)

Espacio de nombres: [Microsoft. Quantum. Research. química](xref:Microsoft.Quantum.Research.Chemistry)

Paquete: [Microsoft. Quantum. Research. química](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Representa un generador dinámico como un conjunto de puertas simulables y una expansión en la base de Pauli.

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a>Entrada

### <a name="parityqubit--qubit"></a>parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit que determina el signo de la evolución del tiempo.



## <a name="output--evolutionset"></a>Salida: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

`EvolutionSet`Que asigna un `GeneratorIndex` para la base de JWOptimized a un ' EvolutionUnitary.