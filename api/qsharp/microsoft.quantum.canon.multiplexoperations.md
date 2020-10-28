---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Operación MultiplexOperations
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 267c9c2858090ebe024fd387938e8bd2f8c76867
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728558"
---
# <a name="multiplexoperations-operation"></a>Operación MultiplexOperations

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una matriz de operaciones controlada por una matriz de Estados numéricos.

Es decir, se aplica la operación unitario controlada por multiplicación $U $ que aplica una $V unitario _j $ cuando se controla mediante $n $-qubit Number State $ \ket{j} $.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="unitaries--t--unit-adj--ctl"></a>unitaries: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL []

Matriz de hasta una operación de hasta $2 ^ n $ unitarios. La operación $j $ TH está indizada por el número $ \ket{j} $ codificado en formato Little-Endian.


### <a name="index--littleendian"></a>Índice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n registro de control $-qubit que codifica los Estados de número $ \ket{j} $ en formato Little-Endian.


### <a name="target--t"></a>destino: ' t

Registro qubit genérico en el que $V _j $ actúa.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="remarks"></a>Observaciones

`coefficients` se rellenará con elementos Identity si se especifican menos de $2 ^ n $. Esta implementación usa $n qubits-$1 auxiliar.

## <a name="references"></a>Referencias

- Hacia la primera simulación de Quantum con la velocidad de Quantum Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su https://arxiv.org/abs/1711.10980