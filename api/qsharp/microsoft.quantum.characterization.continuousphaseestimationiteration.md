---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operación ContinuousPhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728234"
---
# <a name="continuousphaseestimationiteration-operation"></a>Operación ContinuousPhaseEstimationIteration

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Configura [](https://nuget.org/packages/)


Realiza una sola iteración de un algoritmo de estimación de fases iterativo (controlado por clases) que usa poderes reales arbitrarios de una unitario de Oracle.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Operación que actúa en un doble $t $ y un registro, de modo que $U ^ t $ se aplica al registro dado, donde $U $ es la unitario cuya fase se va a estimar y donde $t $ es la potencia del entero que se ha dado a Oracle.


### <a name="time--double"></a>tiempo: [doble](xref:microsoft.quantum.lang-ref.double)

Número de veces que se va a aplicar la unitario de Oracle.


### <a name="theta--double"></a>Theta: [Double](xref:microsoft.quantum.lang-ref.double)

Ángulo por el que se va a invertir la fase en el control qubit antes de actuar en el estado de destino.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro del estado sobre el que ha actuado la unitario de Oracle.


### <a name="controlqubit--qubit"></a>controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

