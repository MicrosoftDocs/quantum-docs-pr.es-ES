---
title: 'Simulador de Quantum Toffoli: kit de desarrollo de Quantum'
description: Obtenga información sobre el simulador de Toffoli de Microsoft QDK, un simulador de Quantum de uso especial que se puede usar con millones de qubits.
author: alan-geller
ms.author: ageller
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 036896a33fa02db671a5fd07421160df164bd41d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690781"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="ea3a8-103">Simulador de Quantum Development Kit (QDK) Toffoli</span><span class="sxs-lookup"><span data-stu-id="ea3a8-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="ea3a8-104">El simulador de Toffoli de QDK es un simulador especial con un ámbito limitado y solo admite `X` `CNOT` operaciones de Quantum de control múltiple, y `X` .</span><span class="sxs-lookup"><span data-stu-id="ea3a8-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="ea3a8-105">Está disponible toda la lógica clásica y los cálculos.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="ea3a8-106">Aunque el simulador Toffoli está más restringido en funcionalidad que el [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), tiene la ventaja de poder simular mucho más qubits.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="ea3a8-107">El simulador Toffoli se puede usar con millones de qubits, mientras que el simulador de estado completo se limita a unos 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="ea3a8-108">Esto resulta útil, por ejemplo, con Oracle que evalúan funciones booleanas, que se pueden implementar con el conjunto limitado de algoritmos admitidos y que se han probado en un gran número de qubits.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="ea3a8-109">Invocar el simulador Toffoli</span><span class="sxs-lookup"><span data-stu-id="ea3a8-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="ea3a8-110">El simulador Toffoli se expone a través de la `ToffoliSimulator` clase.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="ea3a8-111">Para obtener más información, consulte [formas de ejecutar un :::no-loc(Q#)::: programa](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="ea3a8-111">For additional details, see [Ways to run a :::no-loc(Q#)::: program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="ea3a8-112">Invocar el simulador Toffoli de C #</span><span class="sxs-lookup"><span data-stu-id="ea3a8-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="ea3a8-113">Al igual que con otras máquinas de destino, primero se crea una instancia de la clase `ToffoliSimulator` y, a continuación, se pasa como el primer parámetro del método `Run` de una operación.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="ea3a8-114">Tenga en cuenta que, a diferencia de la clase `QuantumSimulator`, la clase `ToffoliSimulator` no implementa la interfaz <xref:System.IDisposable> y, por lo tanto, no es necesario encerrarla dentro de una instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="ea3a8-115">Invocar el simulador Toffoli desde Python</span><span class="sxs-lookup"><span data-stu-id="ea3a8-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="ea3a8-116">Use el método [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) de la biblioteca de Python con la :::no-loc(Q#)::: operación importada:</span><span class="sxs-lookup"><span data-stu-id="ea3a8-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported :::no-loc(Q#)::: operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="ea3a8-117">Invocar el simulador Toffoli desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="ea3a8-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="ea3a8-118">Al ejecutar un :::no-loc(Q#)::: programa desde la línea de comandos, use el parámetro **--Simulator** (o **-s** Shortcut) para especificar el equipo de destino del simulador Toffoli.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-118">When running a :::no-loc(Q#)::: program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="ea3a8-119">El siguiente comando ejecuta un programa mediante el estimador de recursos:</span><span class="sxs-lookup"><span data-stu-id="ea3a8-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="ea3a8-120">Invocación del simulador de Toffoli desde cuadernos de Juptyer</span><span class="sxs-lookup"><span data-stu-id="ea3a8-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="ea3a8-121">Use el :::no-loc(Q#)::: comando "Magic" [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) para ejecutar la :::no-loc(Q#)::: operación.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-121">Use the I:::no-loc(Q#)::: magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the :::no-loc(Q#)::: operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="ea3a8-122">Operaciones compatibles</span><span class="sxs-lookup"><span data-stu-id="ea3a8-122">Supported operations</span></span>

<span data-ttu-id="ea3a8-123">El simulador Toffoli admite:</span><span class="sxs-lookup"><span data-stu-id="ea3a8-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="ea3a8-124">Rotations y un exponente Paulis, como `R` y `Exp` , cuando la operación resultante es igual `X` o la matriz de identidad.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="ea3a8-125">Operaciones de medición y [aserción](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) , pero solo en la `Z` base de Pauli.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-125">Measurement and [assert](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="ea3a8-126">Tenga en cuenta que la probabilidad de una operación de medición siempre es **0** o **1** ; no hay aleatoriedad en el simulador Toffoli.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-126">Note that a measurement operation's probability is always either **0** or **1** ; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="ea3a8-127">`DumpMachine``DumpRegister`funciones y.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="ea3a8-128">Ambas funciones generan el `Z` Estado de base actual de cada qubit, un qubit por línea.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="ea3a8-129">Especificar el número de qubits</span><span class="sxs-lookup"><span data-stu-id="ea3a8-129">Specifying the number of qubits</span></span>

<span data-ttu-id="ea3a8-130">De forma predeterminada, una `ToffoliSimulator` instancia de asigna espacio para 65.536 qubits.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="ea3a8-131">Si el algoritmo requiere más qubits que este, puede especificar el recuento de qubit proporcionando un valor para el `qubitCount` parámetro al constructor.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="ea3a8-132">Cada qubit adicional requiere un solo byte de memoria, por lo que no hay ningún costo significativo en la estimación del número de qubits que necesitará.</span><span class="sxs-lookup"><span data-stu-id="ea3a8-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="ea3a8-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ea3a8-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="ea3a8-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea3a8-134">See also</span></span>

- [<span data-ttu-id="ea3a8-135">Estimador de recursos Quantum</span><span class="sxs-lookup"><span data-stu-id="ea3a8-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="ea3a8-136">Simulador de seguimiento de Quantum</span><span class="sxs-lookup"><span data-stu-id="ea3a8-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="ea3a8-137">Simulador de estado completo de Quantum</span><span class="sxs-lookup"><span data-stu-id="ea3a8-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 