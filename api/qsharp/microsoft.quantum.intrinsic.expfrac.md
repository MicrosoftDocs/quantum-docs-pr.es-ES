---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: Operación ExpFrac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726693"
---
# <a name="expfrac-operation"></a>Operación ExpFrac

Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Configura [](https://nuget.org/packages/)


Aplica el valor exponencial de un operador Pauli de varios qubit con un argumento proporcionado por una fracción Dyadic.

\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align} donde $P _i $ es el elemento $i $ TH de y `paulis` donde $N = $ `Length(paulis)` .

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matriz de valores de Pauli de qubit único que indican los factores del producto tensores en cada qubit.


### <a name="numerator--int"></a>Numerador: [int](xref:microsoft.quantum.lang-ref.int)

Numerador ($k $) en la representación de la fracción de Dyadic del ángulo por el que se va a girar el registro qubit.


### <a name="power--int"></a>potencia: [int](xref:microsoft.quantum.lang-ref.int)

Potencia de dos ($n $) que especifica el denominador del ángulo por el que se va a girar el registro qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Regístrese para aplicar el giro determinado a.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

