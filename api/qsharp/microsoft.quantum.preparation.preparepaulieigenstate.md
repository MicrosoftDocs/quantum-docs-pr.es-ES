---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: Operación PreparePauliEigenstate
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: 473bb2fa4429a14f69bcae4573354aad87dc37df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854356"
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



## <a name="example"></a>Ejemplo

Para preparar un qubit en el estado $ \ket{+} $:

```qsharp
using (q = Qubit()) {
    PreparePauliEigenstate(PauliX, qubit);
    // ...
}
```