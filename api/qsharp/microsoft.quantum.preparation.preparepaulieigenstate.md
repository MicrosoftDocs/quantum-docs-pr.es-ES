---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: Operación PreparePauliEigenstate
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: b24852bb3a455a9fe04b3535156d0c3dfb1a7d12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193699"
---
# <a name="preparepaulieigenstate-operation"></a>Operación PreparePauliEigenstate

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prepara un qubit en el eigenstate positivo de un operador Pauli determinado.
Si se proporciona el operador de identidad, el qubit se prepara en el estado de mezcla máxima.

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a>Descripción

Si el qubit estaba inicialmente en el estado $ \ket {0} $, esta operación prepara el qubit en el eigenstate $ + $1 de un operador Pauli determinado, o bien, para `PauliI` , en el estado de mezcla máxima en su lugar (vea <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Si el qubit estaba en un Estado distinto de $ \ket {0} $, esta operación aplica las siguientes puertas: $H $ para `PauliX` , $HS $ para `PauliY` , $I $ para `PauliZ` y <xref:microsoft.quantum.preparation.preparesinglequbitidentity> para `PauliI` .

## <a name="input"></a>Entrada

### <a name="basis--pauli"></a>base: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Un operador Pauli $P $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit que se va a preparar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

