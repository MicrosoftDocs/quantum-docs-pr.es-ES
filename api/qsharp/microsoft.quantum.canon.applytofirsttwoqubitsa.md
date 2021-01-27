---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: Operación ApplyToFirstTwoQubitsA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 197f1da6682b100a0b71f3548727188c0ef6f7c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850676"
---
# <a name="applytofirsttwoqubitsa-operation"></a>Operación ApplyToFirstTwoQubitsA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación a los dos primeros qubits del registro.
El modificador `A` indica que la operación es adjointable.

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="op--qubitqubit--unit--is-adj"></a>OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ

Operación que se va a aplicar a los dos primeros qubits


### <a name="register--qubit"></a>registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit matriz a las dos primeras qubits de la que se aplica la operación.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Esto equivale a:

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToFirstTwoQubits](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)