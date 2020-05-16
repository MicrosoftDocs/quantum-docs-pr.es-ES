---
title: Estimador de recursos del kit de desarrollo de Quantum
description: 'Obtenga información sobre el estimador de recursos, que estima los recursos necesarios para ejecutar una instancia determinada de una operación de Q # en un equipo Quantum.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 01d242ed405bdd326f65e534f82ff378a464ee7d
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426874"
---
# <a name="the-resources-estimator-target-machine"></a><span data-ttu-id="88694-103">El equipo de destino del estimador de recursos</span><span class="sxs-lookup"><span data-stu-id="88694-103">The Resources Estimator Target Machine</span></span>

<span data-ttu-id="88694-104">Como implica el nombre, el `ResourcesEstimator` calcula los recursos necesarios para ejecutar una instancia determinada de una operación Q # en un equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="88694-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="88694-105">Para ello, se ejecuta la operación Quantum sin simular realmente el estado de un equipo Quantum; por esta razón, puede calcular los recursos de las operaciones de Q # que usan miles de qubits, si la parte clásica del código se puede ejecutar en un momento razonable.</span><span class="sxs-lookup"><span data-stu-id="88694-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits, if the classical part of the code can be run in a reasonable time.</span></span>

## <a name="usage"></a><span data-ttu-id="88694-106">Uso</span><span class="sxs-lookup"><span data-stu-id="88694-106">Usage</span></span>

<span data-ttu-id="88694-107">`ResourcesEstimator`Es simplemente otro tipo de máquina de destino, por lo que se puede usar para ejecutar cualquier operación de Q #.</span><span class="sxs-lookup"><span data-stu-id="88694-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="88694-108">Como otras máquinas de destino, para usarla en un programa host de C#, cree una instancia y pásela como el primer parámetro del método de la operación `Run` :</span><span class="sxs-lookup"><span data-stu-id="88694-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="88694-109">Como se muestra en el ejemplo, `ResourcesEstimator` proporciona un `ToTSV()` método para generar una tabla con valores separados por tabulaciones (TSV) que se puede guardar en un archivo o escribir en la consola para su análisis.</span><span class="sxs-lookup"><span data-stu-id="88694-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-seperated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="88694-110">La salida del programa anterior debería tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="88694-110">The output of the above program should look something like this:</span></span>

```Output
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
> <span data-ttu-id="88694-111">No `ResourcesEstimator` restablece los cálculos en cada ejecución, si se usa la misma instancia para ejecutar otra operación, mantendrá los recuentos agregados sobre los resultados existentes.</span><span class="sxs-lookup"><span data-stu-id="88694-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="88694-112">Si necesita restablecer los cálculos entre ejecuciones, cree una nueva instancia de para cada ejecución.</span><span class="sxs-lookup"><span data-stu-id="88694-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="88694-113">Recuperación de los datos estimados mediante programación</span><span class="sxs-lookup"><span data-stu-id="88694-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="88694-114">Además de una tabla TSV, los recursos estimados se pueden recuperar mediante programación a través de la `ResourcesEstimator` `Data` propiedad de.</span><span class="sxs-lookup"><span data-stu-id="88694-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="88694-115">`Data`proporciona una `System.DataTable` instancia con dos columnas: `Metric` y `Sum` , indizadas por los nombres de las métricas.</span><span class="sxs-lookup"><span data-stu-id="88694-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="88694-116">En el código siguiente se muestra cómo recuperar e imprimir el número total de y las `QubitClifford` `T` `CNOT` puertas utilizadas por una operación de Q #:</span><span class="sxs-lookup"><span data-stu-id="88694-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="88694-117">Métricas declaradas</span><span class="sxs-lookup"><span data-stu-id="88694-117">Metrics Reported</span></span>

<span data-ttu-id="88694-118">A continuación se muestra la lista de métricas estimadas por `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="88694-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="88694-119">__CNOT__: el recuento de las puertas de CNOT (también conocidas como la puerta Pauli X controlada) ejecutadas.</span><span class="sxs-lookup"><span data-stu-id="88694-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="88694-120">__QubitClifford__: el recuento de cualquier Clifford de qubit único y las puertas de Pauli ejecutadas.</span><span class="sxs-lookup"><span data-stu-id="88694-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="88694-121">__Measure__: el recuento de cualquier medida ejecutada.</span><span class="sxs-lookup"><span data-stu-id="88694-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="88694-122">__R__: el recuento de cualquier rotación de qubit única ejecutada, excluidas las puertas T, Clifford y Pauli.</span><span class="sxs-lookup"><span data-stu-id="88694-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="88694-123">__T__: el recuento de t puertas y sus conjugados, incluida la puerta t, T_x = H. T. h y T_y = HY. t. HY, ejecutada.</span><span class="sxs-lookup"><span data-stu-id="88694-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="88694-124">__Depth__: profundidad del circuito de Quantum ejecutado por la operación Q #.</span><span class="sxs-lookup"><span data-stu-id="88694-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="88694-125">De forma predeterminada, solo se cuentan las puertas T en la profundidad; vea [contador de profundidad](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="88694-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="88694-126">__Width__: número máximo de qubits asignados durante la ejecución de la operación Q #.</span><span class="sxs-lookup"><span data-stu-id="88694-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="88694-127">__BorrowedWidth__: número máximo de qubits prestado dentro de la operación Q #.</span><span class="sxs-lookup"><span data-stu-id="88694-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="88694-128">Proporcionar la probabilidad de los resultados de medidas</span><span class="sxs-lookup"><span data-stu-id="88694-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="88694-129"><xref:microsoft.quantum.intrinsic.assertprob>desde el <xref:microsoft.quantum.intrinsic> espacio de nombres se puede usar para proporcionar información sobre la probabilidad esperada de una medida que ayude a impulsar la ejecución del programa de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="88694-129"><xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="88694-130">Esto se ilustra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="88694-130">The following example illustrates this:</span></span>

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

<span data-ttu-id="88694-131">Cuando los `ResourcesEstimator` encuentre `AssertProb` , registrará la medición `PauliZ` en `source` y `q` se le debe proporcionar un resultado de `Zero` con la probabilidad 0,5.</span><span class="sxs-lookup"><span data-stu-id="88694-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="88694-132">Cuando se ejecute `M` más tarde, buscará los valores registrados de las probabilidades de resultado y `M` devolverá `Zero` o `One` con la probabilidad 0,5.</span><span class="sxs-lookup"><span data-stu-id="88694-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="88694-133">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="88694-133">See also</span></span>

<span data-ttu-id="88694-134">`ResourcesEstimator`Se basa en el [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipos Quantum, que proporciona un conjunto más completo de métricas, la capacidad de notificar métricas en el gráfico de llamadas completo y características como el [Comprobador de entradas distintas](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) para ayudar a encontrar errores en los programas de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="88694-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="88694-135">Consulte la documentación del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="88694-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

