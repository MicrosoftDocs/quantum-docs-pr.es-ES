---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Operación ApplyFermionicSWAP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729620"
---
# <a name="applyfermionicswap-operation"></a>Operación ApplyFermionicSWAP

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica el intercambio de Fermionic.

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a>Descripción

Básicamente intercambia el qubits mientras se aplica una fase global de-1 si ambos qubits son 1. Conserva symmetrization de órbitas.
Para obtener más información, vea .

Esta operación está representada por el operador unitario \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 & 1 & 0 & 0 0 & 0 & \\ \\ \\ \\ 0 &-1 \\ \\ \end{bmatrix}.
\end{align}

## <a name="input"></a>Entrada

### <a name="qubit1--qubit"></a>qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primer qubit que se va a intercambiar.


### <a name="qubit2--qubit"></a>qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Segundo qubit que se va a intercambiar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencias

- [*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv: 1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Intrinsic. SWAP](xref:Microsoft.Quantum.Intrinsic.SWAP)