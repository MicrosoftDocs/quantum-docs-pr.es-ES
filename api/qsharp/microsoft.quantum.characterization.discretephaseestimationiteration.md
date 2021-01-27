---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: Operación DiscretePhaseEstimationIteration
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 03e2300dcc2d2cb42992e074833c8cd2530e898b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839974"
---
# <a name="discretephaseestimationiteration-operation"></a>Operación DiscretePhaseEstimationIteration

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Realiza una sola iteración de un algoritmo de estimación de fase iterativo (controlado por clases) con potencias enteras de una clase unitario de Oracle.

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operación que actúa en un entero y un registro, de modo que $U ^ m $ se aplica al registro dado, donde $U $ es la unidad de medida cuya fase se va a estimar y donde $m $ es la potencia del entero que se da a Oracle.


### <a name="power--int"></a>potencia: [int](xref:microsoft.quantum.lang-ref.int)

Número de veces que se va a aplicar la unitario de Oracle.


### <a name="theta--double"></a>Theta: [Double](xref:microsoft.quantum.lang-ref.double)

Ángulo por el que se va a invertir la fase en el control qubit antes de actuar en el estado de destino.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro del estado sobre el que ha actuado la unitario de Oracle.


### <a name="controlqubit--qubit"></a>controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit auxiliar que se usa para controlar la aplicación de la determinada Oracle.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

