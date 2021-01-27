---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Operación QuantumPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 4bdf3de9dab20fa97ba47f15efec4b41a10709f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839670"
---
# <a name="quantumphaseestimation-operation"></a>Operación QuantumPhaseEstimation

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Realiza el algoritmo de estimación de fase de Quantum para una determinada Oracle `U` y `targetState` lee la fase en un registro Quantum Big-Endian.

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Una operación que implementa $U ^ m $ para un entero determinado potencia m.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro de Quantum que representa el estado $ \ket{\phi} $ en el que actuó $U $. Si $ \ket{\phi} $ es un eigenstate de $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ para $ \phi \en [0, 2 \ PI) $ una fase desconocida.


### <a name="controlregister--bigendian"></a>controlRegister: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Un registro entero de representación Big-Endian que se puede utilizar para controlar la Oracle proporcionada y que contendrá la representación de $ \phi $ después de la aplicación de esta operación. Se supone que el controlRegister se inicia en el estado inicial $ \ket{00\cdots 0} $, donde la longitud del registro indica la precisión deseada.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

