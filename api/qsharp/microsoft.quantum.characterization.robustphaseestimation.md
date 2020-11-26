---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: Operación RobustPhaseEstimation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 3e6774e2fe348668840cdc08fe3a070ec3d82a6d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216088"
---
# <a name="robustphaseestimation-operation"></a>Operación RobustPhaseEstimation

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Realiza el robusto algoritmo de estimación de fase de Quantum no iterativo para un determinado Oracle `U` y eigenstate, y proporciona una única estimación de valor real de la fase con ajuste de la varianza en el límite de Heisenberg.

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Entrada

### <a name="bitsprecision--int"></a>bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)

Esto proporciona una estimación de $ \phi $ con la desviación estándar $ \sigma \le 2 \ pi/2 ^ \text{bitsPrecision} $ mediante un número de consultas que escalan como $ \sigma \le 10,7 \pi/\text{# de consultas} $.


### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Una operación que implementa $U ^ m $ para los enteros especificados $m $.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro de Quantum en el que $U $ actúa. Si almacena un eigenstate $ \ket{\phi} $ de $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ para $ \phi\in (-\pi, \pi] $ una fase desconocida.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observaciones

En el límite de un gran número de consultas, Cramer-Rao límites inferiores para la desviación estándar de la estimación de $ \phi $ satisfaga $ \sigma \ge 2 \pi/\text{n.º de consultas} $.

## <a name="references"></a>Referencias

- Calibración sólida de un Single-Qubit universal Gate-Set a través de una sólida estimación de fase de Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677