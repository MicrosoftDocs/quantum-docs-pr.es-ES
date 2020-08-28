---
title: 'Estimador de recursos Quantum: kit de desarrollo de Quantum'
description: Obtenga información sobre el estimador de recursos QDK de Microsoft, que estima los recursos necesarios para ejecutar una instancia determinada de una Q# operación en un equipo Quantum.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1892431c3e332385a5bcefa357eb64a9fac3f381
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992248"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Estimador de recursos del kit de desarrollo de Quantum (QDK)

Como implica el nombre, la `ResourcesEstimator` clase calcula los recursos necesarios para ejecutar una instancia determinada de una Q# operación en un equipo Quantum. Para ello, se ejecuta la operación Quantum sin simular realmente el estado de un equipo Quantum; por esta razón, calcula los recursos para Q# las operaciones que usan miles de qubits, siempre que la parte clásica del código se ejecute en un momento razonable.

El estimador de recursos se basa en el [simulador de seguimiento de Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro), que proporciona un conjunto más completo de métricas y herramientas para ayudar a depurar Q# programas.

## <a name="invoking-and-running-the-resources-estimator"></a>Invocar y ejecutar el estimador de recursos

Puede usar el estimador de recursos para ejecutar cualquier Q# operación. Para obtener más información, consulte [formas de ejecutar un Q# programa](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Invocar al estimador de recursos desde C # 

Al igual que con otras máquinas de destino, primero se crea una instancia de la clase `ResourceEstimator` y, a continuación, se pasa como el primer parámetro del método `Run` de una operación.

Tenga en cuenta que, a diferencia de la clase `QuantumSimulator`, la clase `ResourceEstimator` no implementa la interfaz <xref:System.IDisposable> y, por lo tanto, no es necesario encerrarla dentro de una instrucción `using`.

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

Como se muestra en el ejemplo, `ResourcesEstimator` proporciona el `ToTSV()` método, que genera una tabla con valores separados por tabulaciones (TSV). Puede guardar la tabla en un archivo o mostrarla en la consola para su análisis. A continuación se muestra una salida de ejemplo del programa anterior:

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
> Una `ResourcesEstimator` instancia de no restablece los cálculos en cada ejecución. Si usa la misma instancia para ejecutar otra operación, agrega los nuevos resultados con los resultados existentes. Si necesita restablecer los cálculos entre ejecuciones, cree una nueva instancia para cada ejecución.

### <a name="invoking-the-resources-estimator-from-python"></a>Invocación del estimador de recursos desde Python

Use el método [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) de la biblioteca de Python con la Q# operación importada:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Invocar el estimador de recursos desde la línea de comandos

Al ejecutar un Q# programa desde la línea de comandos, use el parámetro **--Simulator** (o **-s** Shortcut) para especificar el `ResourcesEstimator` equipo de destino. El siguiente comando ejecuta un programa mediante el estimador de recursos: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Invocación del estimador de recursos desde cuadernos de Juptyer Notebook

Use la Q# [estimación del%](xref:microsoft.quantum.iqsharp.magic-ref.simulate) de comandos mágico para ejecutar la Q# operación.

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Recuperación de los datos estimados mediante programación

Además de una tabla TSV, puede recuperar mediante programación los recursos estimados durante la ejecución a través `Data` de la propiedad del estimador de recursos. La `Data` propiedad proporciona una `System.DataTable` instancia con dos columnas: `Metric` y `Sum` , indizadas por los nombres de las métricas.

En el código siguiente se muestra cómo recuperar e imprimir el número total `QubitClifford` de `T` `CNOT` operaciones y utilizadas por una Q# operación:

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

## <a name="metrics-reported"></a>Métricas declaradas

El estimador de recursos realiza un seguimiento de las métricas siguientes:

|Métrica|Descripción|
|----|----|
|__CNOT__    |Recuento de ejecuciones de `CNOT` operaciones (también conocidas como operaciones Pauli X controladas).|
|__QubitClifford__ |El recuento de ejecuciones de todas las operaciones qubit Clifford y Pauli.|
|__Medida__    |Recuento de ejecuciones de cualquier medida.  |
|__R__    |Recuento de ejecuciones de cualquier rotación de un solo qubit, excluidas `T` las operaciones Clifford y Pauli.  |
|__T__    |El recuento de ejecuciones de `T` operaciones y sus conjugaciones, incluidas las `T` operaciones, T_x = H. T. h y T_y = HY. t. HY.  |
|__Profundidad__|Límite inferior de la profundidad del circuito de Quantum ejecutado por la Q# operación. De forma predeterminada, la métrica de profundidad solo cuenta las `T` puertas. Para obtener más información, vea [contador de profundidad](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Width__    |Límite inferior para el número máximo de qubits asignado durante la ejecución de la Q# operación. Es posible que no sea posible conseguir límites inferiores de __profundidad__ y __ancho__ simultáneamente.  |
|__BorrowedWidth__    |Número máximo de qubits prestado dentro de la Q# operación.  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Probabilidad de los resultados de una medición

Puede usar <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> desde el <xref:microsoft.quantum.diagnostics> espacio de nombres para proporcionar información sobre la probabilidad esperada de una operación de medición. Para obtener más información, consulte [simulador de seguimiento de Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .

## <a name="see-also"></a>Consulte también

- [Simulador de seguimiento de Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulador cuántico de Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulador cuántico de estado completo](xref:microsoft.quantum.machines.full-state-simulator) 