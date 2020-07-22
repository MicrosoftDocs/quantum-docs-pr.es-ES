---
title: 'Estimador de recursos Quantum: kit de desarrollo de Quantum'
description: 'Obtenga información sobre el estimador de recursos de Microsoft QDK, que estima los recursos necesarios para ejecutar una instancia determinada de una operación de Q # en un equipo Quantum.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 0909a050e89d6295664e54ab63cfda5d407a8f12
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870554"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="b9458-103">Estimador de recursos del kit de desarrollo de Quantum (QDK)</span><span class="sxs-lookup"><span data-stu-id="b9458-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="b9458-104">Como implica el nombre, la `ResourcesEstimator` clase calcula los recursos necesarios para ejecutar una instancia determinada de una operación de Q # en un equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="b9458-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="b9458-105">Para ello, se ejecuta la operación Quantum sin simular realmente el estado de un equipo Quantum; por esta razón, calcula los recursos de las operaciones de Q # que usan miles de qubits, siempre que la parte clásica del código se ejecute en un momento razonable.</span><span class="sxs-lookup"><span data-stu-id="b9458-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="b9458-106">El estimador de recursos se basa en el [simulador de seguimiento de Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro), que proporciona un conjunto más completo de métricas y herramientas para ayudar a depurar los programas de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="b9458-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="b9458-107">Invocar y ejecutar el estimador de recursos</span><span class="sxs-lookup"><span data-stu-id="b9458-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="b9458-108">Puede usar el estimador de recursos para ejecutar cualquier operación de Q #.</span><span class="sxs-lookup"><span data-stu-id="b9458-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="b9458-109">Para obtener más información, consulte [formas de ejecutar un programa de preguntas y respuestas](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="b9458-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="b9458-110">Invocar al estimador de recursos desde C #</span><span class="sxs-lookup"><span data-stu-id="b9458-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="b9458-111">Como con otras máquinas de destino, primero se crea una instancia de la `ResourceEstimator` clase y, a continuación, se pasa como el primer parámetro del método de una operación `Run` .</span><span class="sxs-lookup"><span data-stu-id="b9458-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="b9458-112">Tenga en cuenta que, a diferencia de la `QuantumSimulator` clase, la `ResourceEstimator` clase no implementa la <xref:System.IDisposable> interfaz y, por tanto, no es necesario encerrarla dentro de una `using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b9458-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="b9458-113">Como se muestra en el ejemplo, `ResourcesEstimator` proporciona el `ToTSV()` método, que genera una tabla con valores separados por tabulaciones (TSV).</span><span class="sxs-lookup"><span data-stu-id="b9458-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="b9458-114">Puede guardar la tabla en un archivo o mostrarla en la consola para su análisis.</span><span class="sxs-lookup"><span data-stu-id="b9458-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="b9458-115">A continuación se muestra una salida de ejemplo del programa anterior:</span><span class="sxs-lookup"><span data-stu-id="b9458-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="b9458-116">Una `ResourcesEstimator` instancia de no restablece los cálculos en cada ejecución.</span><span class="sxs-lookup"><span data-stu-id="b9458-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="b9458-117">Si usa la misma instancia para ejecutar otra operación, agrega los nuevos resultados con los resultados existentes.</span><span class="sxs-lookup"><span data-stu-id="b9458-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="b9458-118">Si necesita restablecer los cálculos entre ejecuciones, cree una nueva instancia para cada ejecución.</span><span class="sxs-lookup"><span data-stu-id="b9458-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="b9458-119">Invocación del estimador de recursos desde Python</span><span class="sxs-lookup"><span data-stu-id="b9458-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="b9458-120">Use el método [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) de la biblioteca de Python con la operación Q # importada:</span><span class="sxs-lookup"><span data-stu-id="b9458-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="b9458-121">Invocar el estimador de recursos desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b9458-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="b9458-122">Al ejecutar un programa de preguntas y respuestas desde la línea de comandos, use el parámetro **--Simulator** (o **-s** Shortcut) para especificar el `ResourcesEstimator` equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="b9458-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="b9458-123">El siguiente comando ejecuta un programa mediante el estimador de recursos:</span><span class="sxs-lookup"><span data-stu-id="b9458-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="b9458-124">Invocación del estimador de recursos desde cuadernos de Juptyer Notebook</span><span class="sxs-lookup"><span data-stu-id="b9458-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="b9458-125">Use la [estimación del%](xref:microsoft.quantum.iqsharp.magic-ref.simulate) del comando IQ # Magic para ejecutar la operación Q #.</span><span class="sxs-lookup"><span data-stu-id="b9458-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="b9458-126">Recuperación de los datos estimados mediante programación</span><span class="sxs-lookup"><span data-stu-id="b9458-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="b9458-127">Además de una tabla TSV, puede recuperar mediante programación los recursos estimados durante la ejecución a través `Data` de la propiedad del estimador de recursos.</span><span class="sxs-lookup"><span data-stu-id="b9458-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="b9458-128">La `Data` propiedad proporciona una `System.DataTable` instancia con dos columnas: `Metric` y `Sum` , indizadas por los nombres de las métricas.</span><span class="sxs-lookup"><span data-stu-id="b9458-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="b9458-129">En el código siguiente se muestra cómo recuperar e imprimir el número total `QubitClifford` de `T` `CNOT` operaciones y utilizadas por una operación de Q #:</span><span class="sxs-lookup"><span data-stu-id="b9458-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="b9458-130">Métricas declaradas</span><span class="sxs-lookup"><span data-stu-id="b9458-130">Metrics Reported</span></span>

<span data-ttu-id="b9458-131">El estimador de recursos realiza un seguimiento de las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b9458-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="b9458-132">Métrica</span><span class="sxs-lookup"><span data-stu-id="b9458-132">Metric</span></span>|<span data-ttu-id="b9458-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9458-133">Description</span></span>|
|----|----|
|<span data-ttu-id="b9458-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="b9458-134">__CNOT__</span></span>    |<span data-ttu-id="b9458-135">Recuento de ejecuciones de `CNOT` operaciones (también conocidas como operaciones Pauli X controladas).</span><span class="sxs-lookup"><span data-stu-id="b9458-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="b9458-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="b9458-136">__QubitClifford__</span></span> |<span data-ttu-id="b9458-137">El recuento de ejecuciones de todas las operaciones qubit Clifford y Pauli.</span><span class="sxs-lookup"><span data-stu-id="b9458-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="b9458-138">__medida__</span><span class="sxs-lookup"><span data-stu-id="b9458-138">__Measure__</span></span>    |<span data-ttu-id="b9458-139">Recuento de ejecuciones de cualquier medida.</span><span class="sxs-lookup"><span data-stu-id="b9458-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="b9458-140">__R__</span><span class="sxs-lookup"><span data-stu-id="b9458-140">__R__</span></span>    |<span data-ttu-id="b9458-141">Recuento de ejecuciones de cualquier rotación de un solo qubit, excluidas `T` las operaciones Clifford y Pauli.</span><span class="sxs-lookup"><span data-stu-id="b9458-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="b9458-142">__T__</span><span class="sxs-lookup"><span data-stu-id="b9458-142">__T__</span></span>    |<span data-ttu-id="b9458-143">El recuento de ejecuciones de `T` operaciones y sus conjugaciones, incluidas las `T` operaciones, T_x = H. T. h y T_y = HY. t. HY.</span><span class="sxs-lookup"><span data-stu-id="b9458-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="b9458-144">__Profundidad__</span><span class="sxs-lookup"><span data-stu-id="b9458-144">__Depth__</span></span>|<span data-ttu-id="b9458-145">Límite inferior de la profundidad del circuito de Quantum ejecutado por la operación Q #.</span><span class="sxs-lookup"><span data-stu-id="b9458-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="b9458-146">De forma predeterminada, la métrica de profundidad solo cuenta las `T` puertas.</span><span class="sxs-lookup"><span data-stu-id="b9458-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="b9458-147">Para obtener más información, vea [contador de profundidad](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="b9458-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="b9458-148">__Width__</span><span class="sxs-lookup"><span data-stu-id="b9458-148">__Width__</span></span>    |<span data-ttu-id="b9458-149">Límite inferior para el número máximo de qubits asignado durante la ejecución de la operación Q #.</span><span class="sxs-lookup"><span data-stu-id="b9458-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="b9458-150">Es posible que no sea posible conseguir límites inferiores de __profundidad__ y __ancho__ simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="b9458-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="b9458-151">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="b9458-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="b9458-152">Número máximo de qubits prestado dentro de la operación Q #.</span><span class="sxs-lookup"><span data-stu-id="b9458-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="b9458-153">Proporcionar la probabilidad de los resultados de la medición</span><span class="sxs-lookup"><span data-stu-id="b9458-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="b9458-154">Puede usar <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> desde el <xref:microsoft.quantum.diagnostics> espacio de nombres para proporcionar información sobre la probabilidad esperada de una operación de medición.</span><span class="sxs-lookup"><span data-stu-id="b9458-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="b9458-155">Para obtener más información, consulte [simulador de seguimiento de Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="b9458-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="b9458-156">Consulta también</span><span class="sxs-lookup"><span data-stu-id="b9458-156">See also</span></span>

- [<span data-ttu-id="b9458-157">Simulador de seguimiento de Quantum</span><span class="sxs-lookup"><span data-stu-id="b9458-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="b9458-158">Simulador de Quantum Toffoli</span><span class="sxs-lookup"><span data-stu-id="b9458-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="b9458-159">Simulador de estado completo de Quantum</span><span class="sxs-lookup"><span data-stu-id="b9458-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 