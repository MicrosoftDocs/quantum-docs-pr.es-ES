---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Operación ApplyToFirstQubitC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2659c3a97baa68cb4c1d7781381f89742902594d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217516"
---
# <a name="applytofirstqubitc-operation"></a>Operación ApplyToFirstQubitC

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica la operación OP al primer qubit del registro.
El modificador `C` indica que la operación es controlable.

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit--is-ctl"></a>OP: [Qubit](xref:microsoft.quantum.lang-ref.qubit) la => [unidad](xref:microsoft.quantum.lang-ref.unit) qubit es CTL

Operación que se va a aplicar al primer qubit


### <a name="register--qubit"></a>registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matriz qubit al primer qubit del que se aplica la operación



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToFirstQubit](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)