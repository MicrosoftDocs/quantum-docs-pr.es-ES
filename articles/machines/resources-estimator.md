---
title: Estimador de recursos del kit de desarrollo de Quantum | Microsoft Docs
description: Información general sobre el estimador de recursos del kit de desarrollo de Quantum de Microsoft
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 591e306b3001934bd81342a533e3f6ca25129781
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184991"
---
# <a name="the-resourcesestimator-target-machine"></a>El equipo de destino ResourcesEstimator

Como implica el nombre, el `ResourcesEstimator` calcula los recursos necesarios para ejecutar una instancia determinada de una operación de Q # en un equipo Quantum.
Para ello, se ejecuta la operación Quantum sin simular realmente el estado de un equipo Quantum; por esta razón, puede calcular los recursos de las operaciones de Q # que usan miles de qubits.

## <a name="usage"></a>Uso

El `ResourcesEstimator` es simplemente otro tipo de equipo de destino, por lo que se puede usar para ejecutar cualquier operación de Q #. 

Como otras máquinas de destino, para usarla en un C# programa host, cree una instancia y pásela como el primer parámetro del método `Run` de la operación:

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

Como se muestra en el ejemplo, el `ResourcesEstimator` proporciona un método `ToTSV()` para generar una tabla con valores separados por tabulaciones (TSV) que se puede guardar en un archivo o escribir en la consola para su análisis. La salida del programa anterior debería tener un aspecto similar al siguiente:

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
> En el `ResourcesEstimator` no se restablecen los cálculos en cada ejecución, si se usa la misma instancia para ejecutar otra operación, se conservarán los recuentos agregados sobre los resultados existentes.
> Si necesita restablecer los cálculos entre ejecuciones, cree una nueva instancia de para cada ejecución.


## <a name="programmatically-retrieving-the-estimated-data"></a>Recuperación de los datos estimados mediante programación

Además de una tabla TSV, los recursos estimados se pueden recuperar mediante programación a través de la propiedad `Data` del `ResourcesEstimator`. `Data` proporciona una instancia de `System.DataTable` con dos columnas: `Metric` y `Sum`, indizadas por los nombres de las métricas.

En el código siguiente se muestra cómo recuperar e imprimir el número total de `QubitClifford`, `T` y las puertas de `CNOT` usadas por una operación de Q #:

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

A continuación se muestra la lista de métricas estimadas por el `ResourcesEstimator`:

* __CNOT__: el recuento de las puertas de CNOT (también conocidas como la puerta Pauli X controlada) ejecutadas.
* __QubitClifford__: el recuento de cualquier Clifford de qubit único y las puertas de Pauli ejecutadas.
* __Measure__: el recuento de cualquier medida ejecutada.
* __R__: el recuento de cualquier rotación de qubit única ejecutada, excluidas las puertas T, Clifford y Pauli.
* __T__: el recuento de t puertas y sus conjugados, incluida la puerta t, T_x = H. T. h y T_y = HY. t. HY, ejecutada.
* __Depth__: profundidad del circuito de Quantum ejecutado por la operación Q #. De forma predeterminada, solo se cuentan las puertas T en la profundidad; vea [contador de profundidad](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) para obtener más información.
* __Width__: número máximo de qubits asignados durante la ejecución de la operación Q #.
* __BorrowedWidth__: número máximo de qubits prestado dentro de la operación Q #.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Proporcionar la probabilidad de los resultados de la medición

<xref:microsoft.quantum.primitive.assertprob> del espacio de nombres de <xref:microsoft.quantum.primitive> se puede usar para proporcionar información sobre la probabilidad esperada de una medida que ayude a impulsar la ejecución del programa de preguntas y respuestas. Esto se ilustra en el ejemplo siguiente:

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

Cuando el `ResourcesEstimator` encuentra `AssertProb` registrará que la medición `PauliZ` en `source` y `ancilla` debe recibir el resultado de `Zero` con la probabilidad 0,5. Cuando se ejecuta `M` más adelante, buscará los valores registrados de las probabilidades de resultado y `M` devolverá `Zero` o `One` con probabilidad 0,5.


## <a name="see-also"></a>Vea también

El `ResourcesEstimator` se basa en el [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipos Quantum, que proporciona un conjunto más completo de métricas, la capacidad de notificar métricas en el gráfico de llamadas completo y características como el [Comprobador de entradas distintas](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) para ayudar a encontrar errores en los programas de Q #. Consulte la documentación del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) para obtener más información.

