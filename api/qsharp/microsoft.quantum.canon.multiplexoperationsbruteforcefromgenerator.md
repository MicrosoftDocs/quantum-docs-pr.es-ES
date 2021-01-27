---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: Operación MultiplexOperationsBruteForceFromGenerator
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 395102c7ffffa81d1a9b6cbf29c9cc22fae6057e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852520"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a>Operación MultiplexOperationsBruteForceFromGenerator

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica la operación de unitarios controlada por multiplicación $U $ que aplica una $V unitario _j $ cuando está controlada por el estado de n-qubit número $ \ket{j} $.

$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a>unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> ' t = la [unidad](xref:microsoft.quantum.lang-ref.unit)  de> es ADJ + CTL)

Una tupla en la que el primer elemento `Int` es el número de unitaries $N $ y el segundo elemento `(Int -> ('T => () is Adj + Ctl))` es una función que toma un entero $j $ in $ [0, N-1] $ y genera la operación unitario $V _J $.


### <a name="index--littleendian"></a>Índice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n registro de control $-qubit que codifica los Estados de número $ \ket{j} $ en formato Little-Endian.


### <a name="target--t"></a>destino: ' t

Registro qubit genérico en el que $V _j $ actúa.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="remarks"></a>Observaciones

`coefficients` se rellenará con elementos Identity si se especifican menos de $2 ^ n $. Esta versión se implementa directamente mediante el bucle a través de los operadores unitarios controlados por n.