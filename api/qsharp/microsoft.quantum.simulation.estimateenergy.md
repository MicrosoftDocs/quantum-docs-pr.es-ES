---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: Operación EstimateEnergy
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 0a02a8aad891c45b184b9b18d4e9383236485940
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229501"
---
# <a name="estimateenergy-operation"></a>Operación EstimateEnergy

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Realiza la preparación del estado aplicando un `statePrepUnitary` en una estimación de fase de estado de entrada asignada automáticamente con respecto a `qpeUnitary` en el estado resultante mediante `phaseEstAlgorithm` .

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Número de qubits utilizadas para realizar la simulación.


### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Que representa una preparación del estado para el generador dinámico inicial.


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a>qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL

Un objeto de Oracle que representa un operador unitario $U $ que representa la evolución para el tiempo $ \delta t $ en un generador dinámico con el estado de la base $ \ket{\phi} $ y la energía del estado de la alimentación $E = \phi \\ , \delta t $.


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double) 

Operación que realiza una estimación de la fase en una operación de unitario determinada.
Consulte [estimación de fase iterativa](/quantum/libraries/characterization#iterative-phase-estimation) para obtener más detalles.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)

Una estimación de $ \hat{\phi} $ de la energía de estado de la alimentación $ \phi $ de la energía de estado de la alimentación del generador representada por $U $.