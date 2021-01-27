---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: Operación AssertOperationsEqualInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 7c330ebdc156e60713a734d39a3600ee1326563c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853479"
---
# <a name="assertoperationsequalinplace-operation"></a>Operación AssertOperationsEqualInPlace

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dadas dos operaciones, garantiza que actúan de forma idéntica para todos los Estados de entrada.

Esta aserción se implementa comprobando la acción de las operaciones en todos los Estados del formulario $V _0 \otimes... \otimes V_ {n-1} $, donde $V _k $ es uno de los Estados $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ y $ \ket{i} $ (+ 1 eigenstate del operador Pauli Y).

Esta aserción usa $n $ qubits y requiere varias llamadas de las operaciones que se van a comparar.

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits $n $ en el que `givenU` operan las operaciones `expectedU` .


### <a name="givenu--qubit--unit"></a>givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación en $n $ qubits que se va a comprobar.


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ

Operación de referencia en $n $ qubits con la que `givenU` se va a comparar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencias

La base de los Estados $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ y $ \ket{i} $ es el Chuang-Nielsen base, que se describe en [ *i. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)