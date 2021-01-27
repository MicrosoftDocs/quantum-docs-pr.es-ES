---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Operación PermuteQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 2fbbe0d99ad1383d77cb08ff6b03bcebd8a1971f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852321"
---
# <a name="permutequbits-operation"></a>Operación PermuteQubits

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Se silencia qubits mediante la operación de intercambio.

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="ordering--int"></a>ordenación: [int](xref:microsoft.quantum.lang-ref.int)[]

Describe la nueva ordenación de qubits, donde el qubit en el índice ahora estará en el orden [i].


### <a name="register--qubit"></a>registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro de qubit en el que se va a actuar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Ejemplo

Dado el orden = [2, 1, 0] y el registro $ \ket{\ alpha_0} \ket{\ alpha_1} \ket{\ alpha_2} $, PermuteQubits cambia el registro en $ \ket{\ alpha_2} \ket{\ alpha_1} \ket{\ alpha_0} $

```qsharp
// The following two lines are equivalent
PermuteQubits([2, 1, 0], register);
SWAP(register[0], register[2]);
```