---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operación ContinuousPhaseEstimationIteration
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851907"
---
# <a name="continuousphaseestimationiteration-operation"></a>Operación ContinuousPhaseEstimationIteration

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Realiza una sola iteración de un algoritmo de estimación de fases iterativo (controlado por clases) que usa poderes reales arbitrarios de una unitario de Oracle.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
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

