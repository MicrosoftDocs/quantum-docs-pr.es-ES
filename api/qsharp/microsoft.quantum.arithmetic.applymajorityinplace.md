---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Operación ApplyMajorityInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: c32d7546fb753f78a72479cec11a6ed09c5e6179
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190741"
---
# <a name="applymajorityinplace-operation"></a>Operación ApplyMajorityInPlace

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica la operación de mayoría de tres qubit en contexto en un registro de qubits.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Esta operación calcula la función de mayoría en contexto en 3 qubits.

Si denotamos la salida qubit como $z $ y Qubits de entrada como $x $ y $y $, la operación realiza la transformación siguiente: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Entrada

### <a name="output--qubit"></a>salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primera entrada qubit. Tenga en cuenta que la salida se calcula en contexto y se almacena en este qubit.


### <a name="input--qubit"></a>entrada: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Segundo y tercer qubits de entrada.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

