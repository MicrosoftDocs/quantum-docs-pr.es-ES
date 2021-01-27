---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: c5a6bbe16d2f6a317f6ed6f258077095465995f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840224"
---
# <a name="restrictedtosubregister-function"></a>RestrictedToSubregister función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restringe una operación a una matriz de índices de un registro, es decir, un subregistro.

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación que se va a restringir a un subregistro.


### <a name="idxs--int"></a>idxs: [int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de índices, que indica a qué qubits se restringe la operación.



## <a name="output--qubit--unit"></a>Salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. RestrictedToSubregisterA](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [Microsoft. Quantum. Canon. RestrictedToSubregisterC](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [Microsoft. Quantum. Canon. RestrictedToSubregisterCA](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)