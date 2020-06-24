---
title: Simulador Toffoli del kit de desarrollo de Quantum
description: Obtenga información sobre el simulador de Toffoli de Microsoft QDK, un simulador de Quantum de uso especial que se puede usar con millones de qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276028"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Simulador Toffoli del kit de desarrollo de Quantum

El kit de desarrollo de Quantum proporciona un simulador de Toffoli, que es un simulador especial que puede simular algoritmos de Quantum que están limitados a las operaciones x, CNOT y X Quantum con control múltiple (todos los cálculos y lógica clásicas están disponibles).

Aunque el simulador Toffoli está mucho más restringido en la operación que el [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), puede simular mucho más qubits.
El simulador Toffoli se puede usar con millones de qubits, mientras que el simulador de estado completo suele estar limitado a unos 30.
Puede ejecutar y depurar un conjunto limitado de algoritmos Quantum escritos en Q # en el equipo; por ejemplo, las Oracle que evalúan funciones booleanas se pueden implementar mediante estas puertas y, por tanto, deben comprobarse con un gran número de qubits con este simulador.

Este simulador de Quantum se expone a través de la `ToffoliSimulator` clase.
Para usar el simulador, solo tiene que crear una instancia de esta clase y pasarla al `Run` método de la operación Quantum que desea ejecutar junto con el resto de los parámetros:

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Otras operaciones

`ToffoliSimulator`Admite rotaciones y un exponente Paulis, como `R` y `Exp` , cuando la operación resultante es igual a `X` o a la identidad.

Se admiten las medidas y las aserciones, pero solo en la base de Pauli `Z` .
Tenga en cuenta que la probabilidad de alguna medida siempre es 0 o 1; no hay aleatoriedad en el simulador Toffoli.

Se admiten `DumpMachine` y `DumpRegister`.
Ambos generan el `Z` Estado de base actual de cada qubit, un qubit por línea.

## <a name="qubitcount"></a>QubitCount

De forma predeterminada, asigna `ToffoliSimulator` espacio para 65.536 qubits.
Si el algoritmo requiere más que esto, puede cambiar el número de qubit proporcionando un valor para el `qubitCount` parámetro al constructor.
Cada qubit adicional requiere un byte de memoria adicional, por lo que no hay ningún costo significativo en la estimación del número de qubits que necesitará.

Por ejemplo:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
