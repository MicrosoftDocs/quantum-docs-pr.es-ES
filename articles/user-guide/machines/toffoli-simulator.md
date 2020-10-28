---
title: 'Simulador de Quantum Toffoli: kit de desarrollo de Quantum'
description: Obtenga información sobre el simulador de Toffoli de Microsoft QDK, un simulador de Quantum de uso especial que se puede usar con millones de qubits.
author: alan-geller
ms.author: ageller
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 036896a33fa02db671a5fd07421160df164bd41d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690781"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>Simulador de Quantum Development Kit (QDK) Toffoli

El simulador de Toffoli de QDK es un simulador especial con un ámbito limitado y solo admite `X` `CNOT` operaciones de Quantum de control múltiple, y `X` . Está disponible toda la lógica clásica y los cálculos.

Aunque el simulador Toffoli está más restringido en funcionalidad que el [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), tiene la ventaja de poder simular mucho más qubits. El simulador Toffoli se puede usar con millones de qubits, mientras que el simulador de estado completo se limita a unos 30 qubits. Esto resulta útil, por ejemplo, con Oracle que evalúan funciones booleanas, que se pueden implementar con el conjunto limitado de algoritmos admitidos y que se han probado en un gran número de qubits.

## <a name="invoking-the-toffoli-simulator"></a>Invocar el simulador Toffoli

El simulador Toffoli se expone a través de la `ToffoliSimulator` clase. Para obtener más información, consulte [formas de ejecutar un Q# programa](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-toffoli-simulator-from-c"></a>Invocar el simulador Toffoli de C #

Al igual que con otras máquinas de destino, primero se crea una instancia de la clase `ToffoliSimulator` y, a continuación, se pasa como el primer parámetro del método `Run` de una operación.

Tenga en cuenta que, a diferencia de la clase `QuantumSimulator`, la clase `ToffoliSimulator` no implementa la interfaz <xref:System.IDisposable> y, por lo tanto, no es necesario encerrarla dentro de una instrucción `using`.

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>Invocar el simulador Toffoli desde Python

Use el método [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) de la biblioteca de Python con la Q# operación importada:

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>Invocar el simulador Toffoli desde la línea de comandos

Al ejecutar un Q# programa desde la línea de comandos, use el parámetro **--Simulator** (o **-s** Shortcut) para especificar el equipo de destino del simulador Toffoli. El siguiente comando ejecuta un programa mediante el estimador de recursos: 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>Invocación del simulador de Toffoli desde cuadernos de Juptyer

Use el Q# comando "Magic" [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) para ejecutar la Q# operación.

```
%toffoli myOperation
```

## <a name="supported-operations"></a>Operaciones compatibles

El simulador Toffoli admite:

* Rotations y un exponente Paulis, como `R` y `Exp` , cuando la operación resultante es igual `X` o la matriz de identidad.
* Operaciones de medición y [aserción](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) , pero solo en la `Z` base de Pauli. Tenga en cuenta que la probabilidad de una operación de medición siempre es **0** o **1** ; no hay aleatoriedad en el simulador Toffoli.
* `DumpMachine``DumpRegister`funciones y.
Ambas funciones generan el `Z` Estado de base actual de cada qubit, un qubit por línea.

## <a name="specifying-the-number-of-qubits"></a>Especificar el número de qubits

De forma predeterminada, una `ToffoliSimulator` instancia de asigna espacio para 65.536 qubits.
Si el algoritmo requiere más qubits que este, puede especificar el recuento de qubit proporcionando un valor para el `qubitCount` parámetro al constructor.
Cada qubit adicional requiere un solo byte de memoria, por lo que no hay ningún costo significativo en la estimación del número de qubits que necesitará.

Por ejemplo:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>Consulte también

- [Estimador de recursos Quantum](xref:microsoft.quantum.machines.resources-estimator)
- [Simulador de seguimiento de Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulador de estado completo de Quantum](xref:microsoft.quantum.machines.full-state-simulator) 