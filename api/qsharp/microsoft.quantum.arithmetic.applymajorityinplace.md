---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Operación ApplyMajorityInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731836"
---
# <a name="applymajorityinplace-operation"></a>Operación ApplyMajorityInPlace

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Configura [](https://nuget.org/packages/)


Aplica la operación de mayoría de tres qubit en contexto en un registro de qubits.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
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

