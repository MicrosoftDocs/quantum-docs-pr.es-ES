---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: Operación ApplyToFirstQubitA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 4f0b209988c01076bdd0429d36d98c8060141618
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208846"
---
# <a name="applytofirstqubita-operation"></a>Operación ApplyToFirstQubitA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación a la primera qubit del registro.
El modificador `A` indica que la operación es adjointable.

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit--is-adj"></a>OP: [Qubit](xref:microsoft.quantum.lang-ref.qubit) la => [unidad](xref:microsoft.quantum.lang-ref.unit) qubit es ADJ

Operación que se va a aplicar al primer qubit


### <a name="register--qubit"></a>registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matriz qubit al primer qubit del que se aplica la operación



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToFirstQubit](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)