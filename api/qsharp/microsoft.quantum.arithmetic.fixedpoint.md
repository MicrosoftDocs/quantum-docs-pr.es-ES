---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Tipo definido por el usuario FixedPoint
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 18e85120647c5a1f41ccab5fbfb27ea602a279af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843199"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="d0b9b-102">Tipo definido por el usuario FixedPoint</span><span class="sxs-lookup"><span data-stu-id="d0b9b-102">FixedPoint user defined type</span></span>

<span data-ttu-id="d0b9b-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d0b9b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d0b9b-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d0b9b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d0b9b-105">Representa un registro de qubits que codifica un número de punto fijo.</span><span class="sxs-lookup"><span data-stu-id="d0b9b-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="d0b9b-106">Consta de un entero que es igual al número de qubits a la izquierda del punto binario, es decir, qubits de peso mayor o igual que 1 y un registro de Quantum.</span><span class="sxs-lookup"><span data-stu-id="d0b9b-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

