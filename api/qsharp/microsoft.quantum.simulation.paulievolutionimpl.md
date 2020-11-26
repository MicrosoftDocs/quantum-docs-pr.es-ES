---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: Operación PauliEvolutionImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 868f3eef187e8e993127cfcab21e1574583ac845
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229144"
---
# <a name="paulievolutionimpl-operation"></a><span data-ttu-id="ee237-102">Operación PauliEvolutionImpl</span><span class="sxs-lookup"><span data-stu-id="ee237-102">PauliEvolutionImpl operation</span></span>

<span data-ttu-id="ee237-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ee237-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ee237-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee237-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee237-105">Representa un generador dinámico como un conjunto de puertas simulables y una expansión en la base de Pauli.</span><span class="sxs-lookup"><span data-stu-id="ee237-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

<span data-ttu-id="ee237-106">Para obtener más información, vea [modelado de generador dinámico](/quantum/libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="ee237-106">See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ee237-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="ee237-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="ee237-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="ee237-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="ee237-109">Índice de generador que se va a representar como una evolución de la Pauli.</span><span class="sxs-lookup"><span data-stu-id="ee237-109">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>


### <a name="delta--double"></a><span data-ttu-id="ee237-110">Delta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ee237-110">delta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ee237-111">Un multiplicador de la duración de la evolución del tiempo según el término al que se hace referencia en `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="ee237-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ee237-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ee237-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ee237-113">Registro actuado por el operador de evolución de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ee237-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee237-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee237-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

