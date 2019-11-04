---
title: Simulador Toffoli del kit de desarrollo de Quantum | Microsoft Docs
description: Información general sobre el simulador Toffoli del kit de desarrollo de Quantum de Microsoft
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 26940d1a8fe31f1035e2d23a68940cd999517c6b
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442360"
---
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="010f2-103">Simulador Toffoli del kit de desarrollo de Quantum</span><span class="sxs-lookup"><span data-stu-id="010f2-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="010f2-104">El kit de desarrollo de Quantum proporciona un simulador de Toffoli, que es un simulador especial que puede simular algoritmos de Quantum que están limitados a las operaciones x, CNOT y X Quantum con control múltiple (todos los cálculos y lógica clásicas están disponibles).</span><span class="sxs-lookup"><span data-stu-id="010f2-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="010f2-105">Aunque el simulador Toffoli está mucho más restringido en la operación que el [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), puede simular mucho más qubits.</span><span class="sxs-lookup"><span data-stu-id="010f2-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="010f2-106">El simulador Toffoli se puede usar con millones de qubits, mientras que el simulador de estado completo suele estar limitado a unos 30.</span><span class="sxs-lookup"><span data-stu-id="010f2-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="010f2-107">Puede ejecutar y depurar un conjunto limitado de algoritmos Quantum escritos en Q # en el equipo; por ejemplo, las Oracle que evalúan funciones booleanas se pueden implementar mediante estas puertas y, por tanto, deben comprobarse con un gran número de qubits con este simulador.</span><span class="sxs-lookup"><span data-stu-id="010f2-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="010f2-108">Este simulador de Quantum se expone a través de la clase `ToffoliSimulator`.</span><span class="sxs-lookup"><span data-stu-id="010f2-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="010f2-109">Para usar el simulador, solo tiene que crear una instancia de esta clase y pasarla al método `Run` de la operación Quantum que desea ejecutar junto con el resto de los parámetros:</span><span class="sxs-lookup"><span data-stu-id="010f2-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="010f2-110">Otras operaciones</span><span class="sxs-lookup"><span data-stu-id="010f2-110">Other Operations</span></span>

<span data-ttu-id="010f2-111">El `ToffoliSimulator` admite rotaciones y un exponente Paulis, como `R` y `Exp`, cuando la operación resultante es igual a `X` o a la identidad.</span><span class="sxs-lookup"><span data-stu-id="010f2-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="010f2-112">Se admiten las medidas y las aserciones, pero solo en Pauli `Z` base.</span><span class="sxs-lookup"><span data-stu-id="010f2-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="010f2-113">Tenga en cuenta que la probabilidad de alguna medida siempre es 0 o 1; no hay aleatoriedad en el simulador Toffoli.</span><span class="sxs-lookup"><span data-stu-id="010f2-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="010f2-114">se admiten `DumpMachine` y `DumpRegister`.</span><span class="sxs-lookup"><span data-stu-id="010f2-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="010f2-115">Ambos generan el estado actual de `Z`base de cada qubit, un qubit por línea.</span><span class="sxs-lookup"><span data-stu-id="010f2-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="010f2-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="010f2-116">QubitCount</span></span>

<span data-ttu-id="010f2-117">De forma predeterminada, la `ToffoliSimulator` asigna espacio para 65.536 qubits.</span><span class="sxs-lookup"><span data-stu-id="010f2-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="010f2-118">Si el algoritmo requiere más que esto, puede cambiar el número de qubit proporcionando un valor para el parámetro `qubitCount` al constructor.</span><span class="sxs-lookup"><span data-stu-id="010f2-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="010f2-119">Cada qubit adicional requiere un byte de memoria adicional, por lo que no hay ningún costo significativo en la estimación del número de qubits que necesitará.</span><span class="sxs-lookup"><span data-stu-id="010f2-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="010f2-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="010f2-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
