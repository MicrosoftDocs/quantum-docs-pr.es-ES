---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: Operación DiscretePhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 167b53d7108c64d11a4f258d17e90ba78d7dd8d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728229"
---
# <a name="discretephaseestimationiteration-operation"></a>Operación DiscretePhaseEstimationIteration

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Configura [](https://nuget.org/packages/)


Realiza una sola iteración de un algoritmo de estimación de fase iterativo (controlado por clases) con potencias enteras de una clase unitario de Oracle.

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
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

