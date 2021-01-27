---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: Operación ApplyToSubregister
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: be820c87ee19230713d6c3e5681bbe3678040e95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850471"
---
# <a name="applytosubregister-operation"></a>Operación ApplyToSubregister

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación a un subregistro de un registro, con qubits especificado por una matriz de sus índices.

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación que se va a aplicar al subregistro.


### <a name="idxs--int"></a>idxs: [int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de índices, que indica a qué qubits se aplicará la operación.


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro en el que actúa la operación.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Ejemplo

Cree tres Estados qubit $ \frac {1} {\sqrt {2} } \ket {0} \_ 2 (\ket {0} \_ 1 \ les {0} _3 + \ket {1} \_ 1 \ les {1} _3) $:

```qsharp
    using (register = Qubit[3]) {
        ApplyToSubregister(Exp([PauliX,PauliY],PI() / 4.0,_), [1,3], register);
    }
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToSubregisterA](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [Microsoft. Quantum. Canon. ApplyToSubregisterC](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [Microsoft. Quantum. Canon. ApplyToSubregisterCA](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)