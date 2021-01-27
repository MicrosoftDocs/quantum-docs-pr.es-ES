---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis operación
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: d46c42846066befafda2af22f7b6e861cb260c33
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831005"
---
# <a name="_fliptobasis-operation"></a>_flipToBasis operación

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Aplica unitaries que asigna $ \ket {0} \otimes\cdots\ket {0} $ a $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $, donde $ \ket{\ psi_k} $ depende de `basis[k]` .

La correspondencia entre el valor de `basis[k]` y $ \ket{\ psi_k} $ es la siguiente:

- `basis[k]=0` $ \rightarrow \ket {0} $.
- `basis[k]=1` $ \rightarrow \ket {1} $.
- `basis[k]=2` $ \rightarrow \ket{+} $.
- `basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 eigenstate de Pauli Y).

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="basis--int"></a>base: [int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de identificadores de estado de base de un solo qubit (0 <= ID <= 3), uno para cada elemento de qubits.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit en el que se va a operar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

