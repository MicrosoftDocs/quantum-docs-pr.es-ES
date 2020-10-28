---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Operación ApplyCNOTChainWithTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729677"
---
# <a name="applycnotchainwithtarget-operation"></a>Operación ApplyCNOTChainWithTarget

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Calcula la paridad de una matriz de qubits en un qubit de destino.

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a>Descripción

Si la matriz está inicialmente en el estado $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{Target}}} $, el estado final lo proporciona $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{Target}}} $.

## <a name="input"></a>Entrada

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matriz de qubits en la que se calcula la paridad.


### <a name="targetqubit--qubit"></a>targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit final en el que la paridad de "qubits" es XORed.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

y

```qsharp
ApplyCNOTChain(qs);
```