---
title: Simulador de estado completo del kit de desarrollo de Quantum | Microsoft Docs
description: Información general sobre el simulador de estado completo del kit de desarrollo de Quantum de Microsoft
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184685"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Simulador de estado completo del kit de desarrollo de Quantum

El kit de desarrollo de Quantum proporciona un simulador de Quantum de estado completo similar a [Liq $ UI | \rangle $](http://stationq.github.io/Liquid/) de Microsoft Research.
Este simulador se puede usar para ejecutar y depurar algoritmos Quantum escritos en Q # en el equipo.

Este simulador de Quantum se expone a través de la clase `QuantumSimulator`. Para usar el simulador, solo tiene que crear una instancia de esta clase y pasarla al método `Run` de la operación Quantum que desea ejecutar junto con el resto de los parámetros:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

La clase `QuantumSimulator` implementa <xref:System.IDisposable>, por lo que se debe llamar al método `Dispose` una vez que ya no se use la instancia del simulador. La mejor manera de hacerlo es ajustar el simulador dentro de una instrucción `using`, como en el ejemplo anterior.

## <a name="seed"></a>Propagación

El `QuantumSimulator` utiliza un generador de números aleatorios para simular la aleatoriedad de Quantum. Con fines de prueba, a veces resulta útil tener resultados deterministas. Esto puede lograrse proporcionando un valor de inicialización para el generador de números aleatorios en el constructor del `QuantumSimulator`a través del parámetro `randomNumberGeneratorSeed`:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Subprocesos

En el `QuantumSimulator` se usa [OpenMP](http://www.openmp.org/) para paralelizar el álgebra lineal requerido. De forma predeterminada, OpenMP usa todos los subprocesos de hardware disponibles, lo que significa que los programas con un número pequeño de qubits se ejecutarán lentamente, ya que la coordinación necesaria Dwarf el trabajo real. Esto puede corregirse si se establece la variable de entorno `OMP_NUM_THREADS` en un número pequeño. Como regla general, 1 subproceso es adecuado para un máximo de 4 qubits y, a continuación, un subproceso adicional por qubit es bueno, aunque esto depende en gran medida del algoritmo.

