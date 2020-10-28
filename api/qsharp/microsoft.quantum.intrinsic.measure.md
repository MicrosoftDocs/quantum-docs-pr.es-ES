---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Operación de medida
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 56ddfbe5e63692e477ad75bde6b1b16269ed20c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726680"
---
# <a name="measure-operation"></a>Operación de medida

Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Configura [](https://nuget.org/packages/)


Realiza una medida conjunta de una o varias qubits en las bases de Pauli especificadas.

El resultado de la salida lo proporciona la distribución: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}, \end{align} donde $P _i $ es el elemento $i $ TH de `bases` y donde $N = \texttt{length} (\texttt{bases}) $.
Es decir, la medida devuelve un `Result` $d $ de modo que el eigenvalue del efecto de medición observado es $ (-1) ^ d $.

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a>Entrada

### <a name="bases--pauli"></a>bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matriz de valores de Pauli de qubit único que indican los factores del producto tensores en cada qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro de qubits que se va a medir.



## <a name="output--__invalidresult__"></a>Salida: __no <Result> válido__

`Zero` Si se observa el eigenvalue $ + $1 y `One` si se observa el eigenvalue $-$1.

## <a name="remarks"></a>Observaciones

Si la matriz base y la matriz qubit tienen longitudes diferentes, se producirá un error en la operación.