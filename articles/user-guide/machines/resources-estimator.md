---
title: 'Estimador de recursos Quantum: kit de desarrollo de Quantum'
description: Obtenga información sobre el estimador de recursos QDK de Microsoft, que estima los recursos necesarios para ejecutar una instancia determinada de una Q# operación en un equipo Quantum.
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3aa94c8b34ad7247fbdeab4bf4dcb96ce746014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847459"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="647bd-103">Estimador de recursos del kit de desarrollo de Quantum (QDK)</span><span class="sxs-lookup"><span data-stu-id="647bd-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="647bd-104">Como implica el nombre, la `ResourcesEstimator` clase calcula los recursos necesarios para ejecutar una instancia determinada de una Q# operación en un equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="647bd-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="647bd-105">Para ello, se ejecuta la operación Quantum sin simular realmente el estado de un equipo Quantum. por esta razón, calcula los recursos para Q# las operaciones que usan miles de qubits, siempre que la parte clásica del código se ejecute en un momento razonable.</span><span class="sxs-lookup"><span data-stu-id="647bd-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="647bd-106">El estimador de recursos se basa en el [simulador de seguimiento de Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro), que proporciona un conjunto más completo de métricas y herramientas para ayudar a depurar Q# programas.</span><span class="sxs-lookup"><span data-stu-id="647bd-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="647bd-107">Invocar y ejecutar el estimador de recursos</span><span class="sxs-lookup"><span data-stu-id="647bd-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="647bd-108">Puede usar el estimador de recursos para ejecutar cualquier Q# operación.</span><span class="sxs-lookup"><span data-stu-id="647bd-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="647bd-109">Para obtener más información, consulte [formas de ejecutar un Q# programa](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="647bd-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="647bd-110">Invocar al estimador de recursos desde C #</span><span class="sxs-lookup"><span data-stu-id="647bd-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="647bd-111">Al igual que con otras máquinas de destino, primero se crea una instancia de la clase `ResourcesEstimator` y, a continuación, se pasa como el primer parámetro del método `Run` de una operación.</span><span class="sxs-lookup"><span data-stu-id="647bd-111">As with other target machines, you first create an instance of the `ResourcesEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="647bd-112">Tenga en cuenta que, a diferencia de la clase `QuantumSimulator`, la clase `ResourcesEstimator` no implementa la interfaz <xref:System.IDisposable> y, por lo tanto, no es necesario encerrarla dentro de una instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="647bd-112">Note that, unlike the `QuantumSimulator` class, the `ResourcesEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

<span data-ttu-id="647bd-113">Como se muestra en el ejemplo, `ResourcesEstimator` proporciona el `ToTSV()` método, que genera una tabla con valores separados por tabulaciones (TSV).</span><span class="sxs-lookup"><span data-stu-id="647bd-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="647bd-114">Puede guardar la tabla en un archivo o mostrarla en la consola para su análisis.</span><span class="sxs-lookup"><span data-stu-id="647bd-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="647bd-115">A continuación se muestra una salida de ejemplo del programa anterior:</span><span class="sxs-lookup"><span data-stu-id="647bd-115">The following is a sample output from the preceding program:</span></span>

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> <span data-ttu-id="647bd-116">Una `ResourcesEstimator` instancia de no restablece los cálculos en cada ejecución.</span><span class="sxs-lookup"><span data-stu-id="647bd-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="647bd-117">Si usa la misma instancia para ejecutar otra operación, agrega los nuevos resultados con los resultados existentes.</span><span class="sxs-lookup"><span data-stu-id="647bd-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="647bd-118">Si necesita restablecer los cálculos entre ejecuciones, cree una nueva instancia para cada ejecución.</span><span class="sxs-lookup"><span data-stu-id="647bd-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="647bd-119">Invocación del estimador de recursos desde Python</span><span class="sxs-lookup"><span data-stu-id="647bd-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="647bd-120">Use el método [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) de la biblioteca de Python con la Q# operación importada:</span><span class="sxs-lookup"><span data-stu-id="647bd-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="647bd-121">Invocar el estimador de recursos desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="647bd-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="647bd-122">Al ejecutar un Q# programa desde la línea de comandos, use el parámetro **--Simulator** (o **-s** Shortcut) para especificar el `ResourcesEstimator` equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="647bd-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="647bd-123">El siguiente comando ejecuta un programa mediante el estimador de recursos:</span><span class="sxs-lookup"><span data-stu-id="647bd-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="647bd-124">Invocación del estimador de recursos desde cuadernos de Juptyer Notebook</span><span class="sxs-lookup"><span data-stu-id="647bd-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="647bd-125">Use la Q# [estimación del%](xref:microsoft.quantum.iqsharp.magic-ref.simulate) de comandos mágico para ejecutar la Q# operación.</span><span class="sxs-lookup"><span data-stu-id="647bd-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="647bd-126">Recuperación de los datos estimados mediante programación</span><span class="sxs-lookup"><span data-stu-id="647bd-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="647bd-127">Además de una tabla TSV, puede recuperar mediante programación los recursos estimados durante la ejecución a través `Data` de la propiedad del estimador de recursos.</span><span class="sxs-lookup"><span data-stu-id="647bd-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="647bd-128">La `Data` propiedad proporciona una `System.DataTable` instancia con dos columnas: `Metric` y `Sum` , indizadas por los nombres de las métricas.</span><span class="sxs-lookup"><span data-stu-id="647bd-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="647bd-129">En el código siguiente se muestra cómo recuperar e imprimir el número total `QubitClifford` de `T` `CNOT` operaciones y utilizadas por una Q# operación:</span><span class="sxs-lookup"><span data-stu-id="647bd-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a><span data-ttu-id="647bd-130">Métricas declaradas</span><span class="sxs-lookup"><span data-stu-id="647bd-130">Metrics Reported</span></span>

<span data-ttu-id="647bd-131">El estimador de recursos realiza un seguimiento de las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="647bd-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="647bd-132">Metric</span><span class="sxs-lookup"><span data-stu-id="647bd-132">Metric</span></span>|<span data-ttu-id="647bd-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="647bd-133">Description</span></span>|
|----|----|
|<span data-ttu-id="647bd-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="647bd-134">__CNOT__</span></span>    |<span data-ttu-id="647bd-135">Recuento de ejecuciones de `CNOT` operaciones (también conocidas como operaciones Pauli X controladas).</span><span class="sxs-lookup"><span data-stu-id="647bd-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="647bd-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="647bd-136">__QubitClifford__</span></span> |<span data-ttu-id="647bd-137">El recuento de ejecuciones de todas las operaciones qubit Clifford y Pauli.</span><span class="sxs-lookup"><span data-stu-id="647bd-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="647bd-138">__Medida__</span><span class="sxs-lookup"><span data-stu-id="647bd-138">__Measure__</span></span>    |<span data-ttu-id="647bd-139">Recuento de ejecuciones de cualquier medida.</span><span class="sxs-lookup"><span data-stu-id="647bd-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="647bd-140">__R__</span><span class="sxs-lookup"><span data-stu-id="647bd-140">__R__</span></span>    |<span data-ttu-id="647bd-141">Recuento de ejecuciones de cualquier rotación de un solo qubit, excluidas `T` las operaciones Clifford y Pauli.</span><span class="sxs-lookup"><span data-stu-id="647bd-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="647bd-142">__T__</span><span class="sxs-lookup"><span data-stu-id="647bd-142">__T__</span></span>    |<span data-ttu-id="647bd-143">El recuento de ejecuciones de `T` operaciones y sus conjugaciones, incluidas las `T` operaciones, T_x = H. T. h y T_y = HY. t. HY.</span><span class="sxs-lookup"><span data-stu-id="647bd-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="647bd-144">__Depth__</span><span class="sxs-lookup"><span data-stu-id="647bd-144">__Depth__</span></span>|<span data-ttu-id="647bd-145">Profundidad del circuito de Quantum ejecutado por la Q# operación (vea [más abajo](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="647bd-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="647bd-146">De forma predeterminada, la métrica de profundidad solo cuenta las `T` puertas.</span><span class="sxs-lookup"><span data-stu-id="647bd-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="647bd-147">Para obtener más información, vea [contador de profundidad](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="647bd-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="647bd-148">__Width__</span><span class="sxs-lookup"><span data-stu-id="647bd-148">__Width__</span></span>|<span data-ttu-id="647bd-149">Ancho del circuito de Quantum ejecutado por la Q# operación (vea [más abajo](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="647bd-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="647bd-150">De forma predeterminada, la métrica de profundidad solo cuenta las `T` puertas.</span><span class="sxs-lookup"><span data-stu-id="647bd-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="647bd-151">Para obtener más información, vea [contador de ancho](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="647bd-151">For more details, see [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span></span>   |
|<span data-ttu-id="647bd-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="647bd-152">__QubitCount__</span></span>    |<span data-ttu-id="647bd-153">Límite inferior para el número máximo de qubits asignado durante la ejecución de la Q# operación.</span><span class="sxs-lookup"><span data-stu-id="647bd-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="647bd-154">Es posible que esta métrica no sea compatible con la __profundidad__ (consulte a continuación).</span><span class="sxs-lookup"><span data-stu-id="647bd-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="647bd-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="647bd-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="647bd-156">Número máximo de qubits prestado dentro de la Q# operación.</span><span class="sxs-lookup"><span data-stu-id="647bd-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="647bd-157">Profundidad, ancho y QubitCount</span><span class="sxs-lookup"><span data-stu-id="647bd-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="647bd-158">Las estimaciones de profundidad y ancho detectadas son compatibles entre sí.</span><span class="sxs-lookup"><span data-stu-id="647bd-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="647bd-159">(Anteriormente, ambos números eran factibles, pero se necesitarían circuitos diferentes para la profundidad y el ancho). Actualmente, las métricas de este par se pueden lograr mediante el mismo circuito al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="647bd-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="647bd-160">Se muestran las siguientes métricas:</span><span class="sxs-lookup"><span data-stu-id="647bd-160">The following metrics are reported:</span></span>

<span data-ttu-id="647bd-161">__Profundidad:__ Para la operación raíz: tiempo que se tarda en ejecutarse, suponiendo que las horas de la puerta estén configuradas.</span><span class="sxs-lookup"><span data-stu-id="647bd-161">__Depth:__ For the root operation - time it takes to execute it assuming configured gate times.</span></span>
<span data-ttu-id="647bd-162">Para las operaciones a las que se llama o la diferencia de tiempo de operaciones posterior entre la última hora de disponibilidad de qubit al principio y el final de la operación.</span><span class="sxs-lookup"><span data-stu-id="647bd-162">For operations called or subsequent operations - time difference between the latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="647bd-163">__Ancho:__ Para la operación raíz: el número de qubits que se usa realmente para ejecutarlo (y la operación a la que llama).</span><span class="sxs-lookup"><span data-stu-id="647bd-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="647bd-164">En el caso de las operaciones llamadas o las operaciones posteriores, el número de qubits que se usaron además de los qubits ya usados al principio de la operación.</span><span class="sxs-lookup"><span data-stu-id="647bd-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="647bd-165">Tenga en cuenta que la qubits reusada no contribuye a este número.</span><span class="sxs-lookup"><span data-stu-id="647bd-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="647bd-166">Es decir, si se han lanzado algunos qubits antes de que se inicie la operación A, y todos los qubit solicitados por esta operación (y las operaciones a las que se llama desde) se cumplieron mediante la reutilización de la versión anterior de qubits, el ancho de la operación A se muestra como 0.</span><span class="sxs-lookup"><span data-stu-id="647bd-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="647bd-167">El qubits prestado correctamente no contribuye al ancho.</span><span class="sxs-lookup"><span data-stu-id="647bd-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="647bd-168">__QubitCount:__ Para la operación raíz: número mínimo de qubits que serían suficientes para ejecutar esta operación (y las operaciones a las que se llama desde ella).</span><span class="sxs-lookup"><span data-stu-id="647bd-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="647bd-169">En el caso de las operaciones llamadas o posteriores: número mínimo de qubits que serían suficientes para ejecutar esta operación por separado.</span><span class="sxs-lookup"><span data-stu-id="647bd-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="647bd-170">Este número no incluye qubits de entrada.</span><span class="sxs-lookup"><span data-stu-id="647bd-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="647bd-171">Incluye qubits prestado.</span><span class="sxs-lookup"><span data-stu-id="647bd-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="647bd-172">Se admiten dos modos de operación.</span><span class="sxs-lookup"><span data-stu-id="647bd-172">Two modes of operation are supported.</span></span> <span data-ttu-id="647bd-173">El modo se selecciona estableciendo QCTraceSimulatorConfiguration. OptimizeDepth.</span><span class="sxs-lookup"><span data-stu-id="647bd-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="647bd-174">__OptimizeDepth = false:__ Este es el modo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="647bd-174">__OptimizeDepth=false:__ This is the default mode.</span></span> <span data-ttu-id="647bd-175">Se recomienda a QubitManager reutilizar qubits y volverá a usar qubits liberado antes de asignar nuevos.</span><span class="sxs-lookup"><span data-stu-id="647bd-175">QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="647bd-176">El __ancho__ de la operación raíz se convierte en el ancho mínimo (límite inferior).</span><span class="sxs-lookup"><span data-stu-id="647bd-176">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="647bd-177">Se registra la __profundidad__ compatible en la que se puede lograr.</span><span class="sxs-lookup"><span data-stu-id="647bd-177">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="647bd-178">__QubitCount__ será el mismo que el __ancho__ de la operación raíz, suponiendo que no haya ningún préstamo.</span><span class="sxs-lookup"><span data-stu-id="647bd-178">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

<span data-ttu-id="647bd-179">__OptimizeDepth = true:__ QubitManager se desaconseja de la reutilización de qubit y la optimización basada en la heurística para la reutilización de qubit se realiza durante y después de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="647bd-179">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and heuristic-based optimization for qubit reuse is performed during and after execution.</span></span> <span data-ttu-id="647bd-180">Para la __profundidad__ de la operación raíz se convierte en la profundidad mínima (límite inferior).</span><span class="sxs-lookup"><span data-stu-id="647bd-180">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="647bd-181">Se ha proporcionado un __ancho__ compatible para esta profundidad (ambos se pueden lograr al mismo tiempo).</span><span class="sxs-lookup"><span data-stu-id="647bd-181">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="647bd-182">Para optimizar el ancho, las puertas que se encuentran más adelante en el programa pueden programarse antes de que las puertas se encuentren con anterioridad en el programa, pero las qubits están programadas para reutilizarlas de forma que la profundidad siga siendo mínima.</span><span class="sxs-lookup"><span data-stu-id="647bd-182">To optimize width, gates encountered later in the program may be scheduled before the gates encountered earlier in the program, but qubits are scheduled to be reused in such a way that the depth remains minimal.</span></span> <span data-ttu-id="647bd-183">Como qubits se reutilizan en función de los valores de tiempo, se recomienda que las horas de la puerta se configuren como valores enteros.</span><span class="sxs-lookup"><span data-stu-id="647bd-183">As qubits are reused based on time values, it is recommended that the gate times are configured to be integer values.</span></span> <span data-ttu-id="647bd-184">No se garantiza que el __ancho__ sea óptimo.</span><span class="sxs-lookup"><span data-stu-id="647bd-184">__Width__ is not guaranteed to be optimal.</span></span> <span data-ttu-id="647bd-185">Puede encontrar más información en la [profundidad y el ancho del documento en el seguimiento](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs).</span><span class="sxs-lookup"><span data-stu-id="647bd-185">More information can be found in the whitepaper [Width and Depth in the Tracer](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs).</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="647bd-186">Probabilidad de los resultados de una medición</span><span class="sxs-lookup"><span data-stu-id="647bd-186">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="647bd-187">Puede usar <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> desde el <xref:Microsoft.Quantum.Diagnostics> espacio de nombres para proporcionar información sobre la probabilidad esperada de una operación de medición.</span><span class="sxs-lookup"><span data-stu-id="647bd-187">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="647bd-188">Para obtener más información, consulte [simulador de seguimiento de Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="647bd-188">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="647bd-189">Consulte también</span><span class="sxs-lookup"><span data-stu-id="647bd-189">See also</span></span>

- [<span data-ttu-id="647bd-190">Simulador de seguimiento de Quantum</span><span class="sxs-lookup"><span data-stu-id="647bd-190">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="647bd-191">Simulador cuántico de Toffoli</span><span class="sxs-lookup"><span data-stu-id="647bd-191">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="647bd-192">Simulador cuántico de estado completo</span><span class="sxs-lookup"><span data-stu-id="647bd-192">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
