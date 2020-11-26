---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Operación PrepareChoiState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: ced71c4278f42f577760acd54ae53e7f5e6dae4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210580"
---
# <a name="preparechoistate-operation"></a>Operación PrepareChoiState

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prepara el estado Choi – Jamiołkowski para una operación determinada en determinados registros de referencia y de destino.

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación $ \Lambda $ cuya Choi – Jamiołkowski State $J (\Lambda)/2 ^ N $ se va a preparar, donde $N $ es el número de qubits en el que `op` actúa.


### <a name="reference--qubit"></a>Referencia: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro de qubits a partir del estado $ \ket{00\cdots 0} $ que se va a usar como referencia para la acción de `op` .


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro de qubits inicialmente en el estado $ \ket{00\cdots 0} $ en el que `op` se va a aplicar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Choi – Jamiłkowski State $J (\Lambda) $ de un proceso Quantum se define como $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ Where $ | X\rangle \! \rangle $ es la *vectorización* de una matriz $X $ en la Convención de apilamiento de columnas. El aprendizaje de una descripción clásica de este estado proporciona información completa sobre el efecto de $ \Lambda $ que actúa en Estados de entrada arbitrarios y forma la base del *proceso de Quantum Tomography*.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. preparación. PrepareChoiStateA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [Microsoft. Quantum. preparación. PrepareChoiStateC](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [Microsoft. Quantum. preparación. PrepareChoiStateCA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)