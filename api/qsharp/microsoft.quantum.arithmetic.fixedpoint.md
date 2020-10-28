---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Tipo definido por el usuario FixedPoint
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: f1370cd2f8a7d6488ae0f6be841abd95e61f038e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731533"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="3a822-102">Tipo definido por el usuario FixedPoint</span><span class="sxs-lookup"><span data-stu-id="3a822-102">FixedPoint user defined type</span></span>

<span data-ttu-id="3a822-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3a822-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3a822-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3a822-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3a822-105">Representa un registro de qubits que codifica un número de punto fijo.</span><span class="sxs-lookup"><span data-stu-id="3a822-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="3a822-106">Consta de un entero que es igual al número de qubits a la izquierda del punto binario, es decir, qubits de peso mayor o igual que 1 y un registro de Quantum.</span><span class="sxs-lookup"><span data-stu-id="3a822-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

