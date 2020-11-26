---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Tipo definido por el usuario GeneratorIndex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: dae23db9bee34be4aa99d96799efad64a66d7193
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229331"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="61ecb-102">Tipo definido por el usuario GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="61ecb-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="61ecb-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="61ecb-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="61ecb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61ecb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61ecb-105">Representa un término primitivo único en el conjunto de todos los generadores dinámicos, por ejemplo, los operadores Hermitian, para los que existe una asignación de ese generador a la evolución de tiempo de ese generador, a través de `EvolutionSet` .</span><span class="sxs-lookup"><span data-stu-id="61ecb-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="61ecb-106">El primer elemento (int [], double []) es un índice que tiene un único término; por ejemplo, la cadena Pauli XXY con coeficiente 0,5 sería indexada por ([1, 1, 2], [0,5]).</span><span class="sxs-lookup"><span data-stu-id="61ecb-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="61ecb-107">Como alternativa, Hamiltonians parametrizado mediante una variable continua, como X cos φ + Y sin φ, podría representarse por instancia ([], [φ]).</span><span class="sxs-lookup"><span data-stu-id="61ecb-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="61ecb-108">El segundo elemento indiza el subsistema en el que actúa el generador.</span><span class="sxs-lookup"><span data-stu-id="61ecb-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a><span data-ttu-id="61ecb-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="61ecb-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="61ecb-110">No se define la interpretación de un, `GeneratorIndex` excepto con referencia a un conjunto determinado de generadores.</span><span class="sxs-lookup"><span data-stu-id="61ecb-110">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="61ecb-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61ecb-111">See Also</span></span>

- [<span data-ttu-id="61ecb-112">Microsoft. Quantum. Simulation. EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="61ecb-112">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="61ecb-113">Microsoft. Quantum. Simulation. PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="61ecb-113">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)