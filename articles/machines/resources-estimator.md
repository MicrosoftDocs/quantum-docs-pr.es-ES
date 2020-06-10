---
title: Estimador de recursos del kit de desarrollo de Quantum
description: 'Obtenga información sobre el estimador de recursos, que estima los recursos necesarios para ejecutar una instancia determinada de una operación de Q # en un equipo Quantum.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: b0c800c3946d2e4ba4457127fb9495dc9dcf2934
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630128"
---
# <a name="the-resources-estimator-target-machine"></a>El equipo de destino del estimador de recursos

Como implica el nombre, el `ResourcesEstimator` calcula los recursos necesarios para ejecutar una instancia determinada de una operación Q # en un equipo Quantum.
Para ello, se ejecuta la operación Quantum sin simular realmente el estado de un equipo Quantum; por esta razón, puede calcular los recursos de las operaciones de Q # que usan miles de qubits, si la parte clásica del código se puede ejecutar en un momento razonable.

## <a name="usage"></a>Uso

`ResourcesEstimator`Es simplemente otro tipo de máquina de destino, por lo que se puede usar para ejecutar cualquier operación de Q #. 

Como otras máquinas de destino, para usarla en un programa host de C#, cree una instancia y pásela como el primer parámetro del método de la operación `Run` :

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

Como se muestra en el ejemplo, `ResourcesEstimator` proporciona un `ToTSV()` método para generar una tabla con valores separados por tabulaciones (TSV) que se puede guardar en un archivo o escribir en la consola para su análisis. La salida del programa anterior debería tener un aspecto similar al siguiente:

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
> No `ResourcesEstimator` restablece los cálculos en cada ejecución, si se usa la misma instancia para ejecutar otra operación, mantendrá los recuentos agregados sobre los resultados existentes.
> Si necesita restablecer los cálculos entre ejecuciones, cree una nueva instancia de para cada ejecución.


## <a name="programmatically-retrieving-the-estimated-data"></a>Recuperación de los datos estimados mediante programación

Además de una tabla TSV, los recursos estimados se pueden recuperar mediante programación a través de la `ResourcesEstimator` `Data` propiedad de. `Data`proporciona una `System.DataTable` instancia con dos columnas: `Metric` y `Sum` , indizadas por los nombres de las métricas.

En el código siguiente se muestra cómo recuperar e imprimir el número total de y las `QubitClifford` `T` `CNOT` puertas utilizadas por una operación de Q #:

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

A continuación se muestra la lista de métricas estimadas por `ResourcesEstimator` :

* __CNOT__: el recuento de las puertas de CNOT (también conocidas como la puerta Pauli X controlada) ejecutadas.
* __QubitClifford__: el recuento de cualquier Clifford de qubit único y las puertas de Pauli ejecutadas.
* __Measure__: el recuento de cualquier medida ejecutada.
* __R__: el recuento de cualquier rotación de qubit única ejecutada, excluidas las puertas T, Clifford y Pauli.
* __T__: el recuento de t puertas y sus conjugados, incluida la puerta t, T_x = H. T. h y T_y = HY. t. HY, ejecutada.
* __Depth__: profundidad del circuito de Quantum ejecutado por la operación Q #. De forma predeterminada, solo se cuentan las puertas T en la profundidad; vea [contador de profundidad](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) para obtener más información.
* __Width__: número máximo de qubits asignados durante la ejecución de la operación Q #.
* __BorrowedWidth__: número máximo de qubits prestado dentro de la operación Q #.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Proporcionar la probabilidad de los resultados de medidas

<xref:microsoft.quantum.intrinsic.assertprob>desde el <xref:microsoft.quantum.intrinsic> espacio de nombres se puede usar para proporcionar información sobre la probabilidad esperada de una medida que ayude a impulsar la ejecución del programa de preguntas y respuestas. Esto se ilustra en el ejemplo siguiente:

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

Cuando los `ResourcesEstimator` encuentre `AssertProb` , registrará la medición `PauliZ` en `source` y `q` se le debe proporcionar un resultado de `Zero` con la probabilidad 0,5. Cuando se ejecute `M` más tarde, buscará los valores registrados de las probabilidades de resultado y `M` devolverá `Zero` o `One` con la probabilidad 0,5.


## <a name="see-also"></a>Consulte también

`ResourcesEstimator`Se basa en el [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipos Quantum, que proporciona un conjunto más completo de métricas, la capacidad de notificar métricas en el gráfico de llamadas completo y características como el [Comprobador de entradas distintas](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) para ayudar a encontrar errores en los programas de preguntas y respuestas. Consulte la documentación del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) para obtener más información.

