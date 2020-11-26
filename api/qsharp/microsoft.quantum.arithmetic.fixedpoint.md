---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Tipo definido por el usuario FixedPoint
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 0fea6e4ee1b8c5391e815217f1ddf9e511d46463
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223109"
---
# <a name="fixedpoint-user-defined-type"></a>Tipo definido por el usuario FixedPoint

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Representa un registro de qubits que codifica un número de punto fijo. Consta de un entero que es igual al número de qubits a la izquierda del punto binario, es decir, qubits de peso mayor o igual que 1 y un registro de Quantum.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

