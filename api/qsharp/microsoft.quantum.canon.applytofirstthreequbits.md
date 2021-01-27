---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Operación ApplyToFirstThreeQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: b01c1072306cfdebcb90827a14683a32312481fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850693"
---
# <a name="applytofirstthreequbits-operation"></a>Operación ApplyToFirstThreeQubits

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación a los tres primeros qubits del registro.

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="op--qubitqubitqubit--unit"></a>OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación que se va a aplicar a los tres primeros qubits


### <a name="register--qubit"></a>registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matriz qubit a las tres primeras qubits de la que se aplica la operación.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Esto equivale a:

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsC](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsA](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsCA](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)