---
title: Simulador de estado completo
description: Obtenga información sobre cómo ejecutar los programas de preguntas y respuestas en el Microsoft Quantum Development Kit simulador de estado completo.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275645"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Simulador de estado completo del kit de desarrollo de Quantum

El kit de desarrollo de Quantum proporciona un simulador de Quantum de estado completo similar a [Liq $ UI | \rangle $](http://stationq.github.io/Liquid/) de Microsoft Research.
Este simulador se puede usar para ejecutar y depurar algoritmos Quantum escritos en Q # en el equipo.

Este simulador de Quantum se expone a través de la `QuantumSimulator` clase. Para usar el simulador, solo tiene que crear una instancia de esta clase y pasarla al `Run` método de la operación Quantum que desea ejecutar junto con el resto de los parámetros:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

La `QuantumSimulator` clase implementa <xref:System.IDisposable> , por lo que `Dispose` se debe llamar al método una vez que ya no se use la instancia del simulador. La mejor manera de hacerlo es ajustar el simulador dentro de una `using` instrucción, como en el ejemplo anterior.

## <a name="seed"></a>Seed

`QuantumSimulator`Utiliza un generador de números aleatorios para simular la aleatoriedad de Quantum. Con fines de prueba, a veces resulta útil tener resultados deterministas. Esto puede lograrse proporcionando un valor de inicialización para el generador de números aleatorios en el `QuantumSimulator` constructor de a través del `randomNumberGeneratorSeed` parámetro:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Subprocesos

`QuantumSimulator`Usa [OpenMP](http://www.openmp.org/) para paralelizar el álgebra lineal requerido. De forma predeterminada, OpenMP usa todos los subprocesos de hardware disponibles, lo que significa que, por lo general, los programas con un número reducido de qubits se ejecutarán lentamente, ya que la coordinación necesaria mermará el trabajo real. Esto puede corregirse si se establece la variable de entorno `OMP_NUM_THREADS` en un número pequeño. Como norma general, un subproceso es adecuado para un máximo de 4 qubits aproximadamente y, a partir de ahí, resulta adecuado un subproceso adicional por qubit, aunque esto depende en gran medida del algoritmo.

