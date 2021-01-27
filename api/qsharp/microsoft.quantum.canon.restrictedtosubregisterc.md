---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: RestrictedToSubregisterC función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: f44e9ea4d17dcadc6d3c64941529db819b7f9784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840214"
---
# <a name="restrictedtosubregisterc-function"></a>RestrictedToSubregisterC función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restringe una operación a una matriz de índices de un registro, es decir, un subregistro.
El modificador `C` indica que la operación es controlable.

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit--is-ctl"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL

Operación que se va a restringir a un subregistro.


### <a name="idxs--int"></a>idxs: [int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de índices, que indica a qué qubits se restringe la operación.



## <a name="output--qubit--unit--is-ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. RestrictedToSubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)