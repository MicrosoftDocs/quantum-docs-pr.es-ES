---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Operación PrepareQubit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: e6a88ccf4c01b2f0a7344e3823b2748790cf9650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854336"
---
# <a name="preparequbit-operation"></a>Operación PrepareQubit

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> PrepareQubit está en desuso. Use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> en su lugar.

Prepara un qubit en el eigenstate + 1 ( `Zero` ) del operador Pauli especificado.
Si se proporciona el operador de identidad, el qubit se prepara en el estado de mezcla máxima.

Si el qubit estaba inicialmente en el estado $ \ket {0} $, esta operación prepara el qubit en el eigenstate $ + $1 de un operador Pauli determinado, o bien, para `PauliI` , en el estado de mezcla máxima en su lugar (vea <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Si el qubit estaba en un Estado distinto de $ \ket {0} $, esta operación aplica las siguientes puertas: $H $ para `PauliX` , $HS $ para `PauliY` , $I $ para `PauliZ` y <xref:microsoft.quantum.preparation.preparesinglequbitidentity> para `PauliI` .

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="basis--pauli"></a>base: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Un operador Pauli $P $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit que se va a preparar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

