---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Operación CompareUsingRippleCarry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843284"
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