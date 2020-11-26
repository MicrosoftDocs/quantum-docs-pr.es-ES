---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Operación CompareUsingRippleCarry
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: e2d6e5a663f8c4e101c7e2ab1346d10cade3f4e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223466"
---
# <a name="compareusingripplecarry-operation"></a>Operación CompareUsingRippleCarry

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Esta operación comprueba si un entero representado por un registro de qubits es mayor que otro entero, aplicando un XOR del resultado en una qubit de salida.

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Dado dos enteros `x` y `y` almacenados en registros de qubit de igual tamaño, esta operación comprueba si cumplen `x > y` . Si es true, 1 se XORed en un qubit de salida. De lo contrario, 0 se XORed en un qubit de salida.
En otras palabras, esta operación se puede representar mediante la unitario $ $ \begin{align} U\ket {x} \ les {y} \ les {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.
\end{align} $ $

## <a name="input"></a>Entrada

### <a name="x--littleendian"></a>x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Primer número que se va a comparar en `LittleEndian` formato en un registro qubit.


### <a name="y--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Segundo número que se va a comparar en el `LittleEndian` formato de un registro qubit.


### <a name="output--qubit"></a>salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit que almacena el resultado de la comparación $x>y $.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencias

- Un nuevo circuito de adición de paso de onda de Quantum Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184