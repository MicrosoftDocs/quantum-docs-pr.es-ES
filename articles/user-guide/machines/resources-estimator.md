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
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Estimador de recursos del kit de desarrollo de Quantum (QDK)

Como implica el nombre, la `ResourcesEstimator` clase calcula los recursos necesarios para ejecutar una instancia determinada de una operación de Q # en un equipo Quantum. Para ello, se ejecuta la operación Quantum sin simular realmente el estado de un equipo Quantum; por esta razón, calcula los recursos de las operaciones de Q # que usan miles de qubits, siempre que la parte clásica del código se ejecute en un momento razonable.

El estimador de recursos se basa en el [simulador de seguimiento de Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro), que proporciona un conjunto más completo de métricas y herramientas para ayudar a depurar los programas de preguntas y respuestas.

## <a name="invoking-and-running-the-resources-estimator"></a>Invocar y ejecutar el estimador de recursos

Puede usar el estimador de recursos para ejecutar cualquier operación de Q #. Para obtener más información, consulte [formas de ejecutar un programa de preguntas y respuestas](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Invocar al estimador de recursos desde C # 

Como con otras máquinas de destino, primero se crea una instancia de la `ResourceEstimator` clase y, a continuación, se pasa como el primer parámetro del método de una operación `Run` .

Tenga en cuenta que, a diferencia de la `QuantumSimulator` clase, la `ResourceEstimator` clase no implementa la <xref:System.IDisposable> interfaz y, por tanto, no es necesario encerrarla dentro de una `using` instrucción.

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

Use el método [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) de la biblioteca de Python con la operación Q # importada:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Invocar el estimador de recursos desde la línea de comandos

Al ejecutar un programa de preguntas y respuestas desde la línea de comandos, use el parámetro **--Simulator** (o **-s** Shortcut) para especificar el `ResourcesEstimator` equipo de destino. El siguiente comando ejecuta un programa mediante el estimador de recursos: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Invocación del estimador de recursos desde cuadernos de Juptyer Notebook

Use la [estimación del%](xref:microsoft.quantum.iqsharp.magic-ref.simulate) del comando IQ # Magic para ejecutar la operación Q #.

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Recuperación de los datos estimados mediante programación

Además de una tabla TSV, puede recuperar mediante programación los recursos estimados durante la ejecución a través `Data` de la propiedad del estimador de recursos. La `Data` propiedad proporciona una `System.DataTable` instancia con dos columnas: `Metric` y `Sum` , indizadas por los nombres de las métricas.

En el código siguiente se muestra cómo recuperar e imprimir el número total `QubitClifford` de `T` `CNOT` operaciones y utilizadas por una operación de Q #:

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
|__medida__    |Recuento de ejecuciones de cualquier medida.  |
|__R__    |Recuento de ejecuciones de cualquier rotación de un solo qubit, excluidas `T` las operaciones Clifford y Pauli.  |
|__T__    |El recuento de ejecuciones de `T` operaciones y sus conjugaciones, incluidas las `T` operaciones, T_x = H. T. h y T_y = HY. t. HY.  |
|__Profundidad__|Límite inferior de la profundidad del circuito de Quantum ejecutado por la operación Q #. De forma predeterminada, la métrica de profundidad solo cuenta las `T` puertas. Para obtener más información, vea [contador de profundidad](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Width__    |Límite inferior para el número máximo de qubits asignado durante la ejecución de la operación Q #. Es posible que no sea posible conseguir límites inferiores de __profundidad__ y __ancho__ simultáneamente.  |
|__BorrowedWidth__    |Número máximo de qubits prestado dentro de la operación Q #.  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Proporcionar la probabilidad de los resultados de la medición

Puede usar <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> desde el <xref:microsoft.quantum.diagnostics> espacio de nombres para proporcionar información sobre la probabilidad esperada de una operación de medición. Para obtener más información, consulte [simulador de seguimiento de Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .

## <a name="see-also"></a>Consulta también

- [Simulador de seguimiento de Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulador de Quantum Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulador de estado completo de Quantum](xref:microsoft.quantum.machines.full-state-simulator) 