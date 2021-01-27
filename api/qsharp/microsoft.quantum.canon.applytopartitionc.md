---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: Operación ApplyToPartitionC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 43cf43fa2bf9c00a4096b39555b8f6080dd506d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850525"
---
# <a name="applytopartitionc-operation"></a>Operación ApplyToPartitionC

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica un par de operaciones a una partición determinada de un registro en dos partes.
El modificador `C` indica que la operación es controlable.

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Entrada

### <a name="op--qubitqubit--unit--is-ctl"></a>OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL

Par de operaciones que se van a aplicar a la partición especificada.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)

Número de qubits del destino que se van a colocar en la primera parte de la partición.
El Qubits restante constituye la segunda parte de la partición.


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro de qubits que se va a particionar y en el que se va a realizar la operación con las dos operaciones dadas.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToPartition](xref:Microsoft.Quantum.Canon.ApplyToPartition)