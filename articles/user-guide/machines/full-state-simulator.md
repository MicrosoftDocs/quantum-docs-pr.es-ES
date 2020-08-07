---
title: 'Simulador de Quantum de estado completo: kit de desarrollo de Quantum'
description: Obtenga información sobre cómo ejecutar sus Q# programas en el Microsoft Quantum Development Kit simulador de estado completo.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: b15af66123dadae09815cde1966c69b3ce2e9e64
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868345"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>Simulador de estado completo del kit de desarrollo de Quantum (QDK)

El QDK proporciona un simulador de estado completo que simula una máquina Quantum en el equipo local. Puede usar el simulador de estado completo para ejecutar y depurar algoritmos Quantum escritos en Q# , con un máximo de 30 qubits. El simulador de estado completo es similar al simulador de Quantum usado en la plataforma [Liq $ UI | \rangle $](http://stationq.github.io/Liquid/) de Microsoft Research.

## <a name="invoking-and-running-the-full-state-simulator"></a>Invocar y ejecutar el simulador de estado completo

Expone el simulador de estado completo a través de la `QuantumSimulator` clase. Para obtener más información, consulte [formas de ejecutar un Q# programa](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-simulator-from-c"></a>Invocar el simulador de C #

Cree una instancia de la `QuantumSimulator` clase y, a continuación, pásela al `Run` método de una operación Quantum, junto con los parámetros adicionales.
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

Dado que la `QuantumSimulator` clase implementa la <xref:System.IDisposable> interfaz, debe llamar al `Dispose` método una vez que ya no necesita la instancia del simulador. La mejor manera de hacerlo es encapsular las operaciones y la declaración del simulador dentro de una instrucción [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) , que llama automáticamente al `Dispose` método.

### <a name="invoking-the-simulator-from-python"></a>Invocar el simulador desde Python

Use el método [Simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) de la Q# biblioteca de Python con la Q# operación importada:

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>Invocar el simulador desde la línea de comandos

Al ejecutar un Q# programa desde la línea de comandos, el simulador de estado completo es el equipo de destino predeterminado. Opcionalmente, puede usar el parámetro **--Simulator** (o **-s** Shortcut) para especificar el equipo de destino deseado. Los dos comandos siguientes ejecutan un programa mediante el simulador de estado completo. 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>Invocación del simulador de cuadernos de Juptyer Notebook

Use la instrucción I Q# mágica [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) para ejecutar la Q# operación.

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>Propagación del simulador

De forma predeterminada, el simulador de estado completo utiliza un generador de números aleatorios para simular la aleatoriedad de Quantum. Con fines de prueba, a veces resulta útil tener resultados deterministas. En un programa de C#, puede lograrlo proporcionando un valor de inicialización para el generador de números aleatorios en el `QuantumSimulator` constructor a través del `randomNumberGeneratorSeed` parámetro.

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>Configuración de subprocesos

El simulador de estado completo utiliza [OpenMP](http://www.openmp.org/) para paralelizar el álgebra lineal requerido. De forma predeterminada, OpenMP usa todos los subprocesos de hardware disponibles, lo que significa que los programas con un número pequeño de qubits suelen ejecutarse lentamente porque la coordinación necesaria Dwarfs el trabajo real. Puede corregir esto si establece la variable de entorno `OMP_NUM_THREADS` en un número pequeño. Como regla general, configure un subproceso para un máximo de cuatro qubits y, a continuación, un subproceso adicional por qubit. Es posible que deba ajustar la variable según el algoritmo.

## <a name="see-also"></a>Consulte también

- [Estimador de recursos cuánticos](xref:microsoft.quantum.machines.resources-estimator)
- [Simulador cuántico de Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulador de seguimiento de Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)