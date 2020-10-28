---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: Operación MultiplexOperationsFromGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2fde0bf391568f39128e6dca4b535aa6b78407c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728541"
---
# <a name="multiplexoperationsfromgenerator-operation"></a>Operación MultiplexOperationsFromGenerator

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación de unitario con control de multiplicación $U $ que aplica una $V unitario _j $ cuando está controlada por el estado de n-qubit número $ \ket{j} $.

$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a>unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) ajustable + CTL)

Una tupla en la que el primer elemento `Int` es el número de unitaries $N $ y el segundo elemento `(Int -> ('T => () is Adj + Ctl))` es una función que toma un entero $j $ in $ [0, N-1] $ y genera la operación unitario $V _J $.


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

- [*Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su* , arXiv: 1711.10980](https://arxiv.org/abs/1711.10980)