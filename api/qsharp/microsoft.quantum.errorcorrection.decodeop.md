---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: Tipo definido por el usuario DecodeOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: 0733ec016e50a320b162b111c7d87c32140fdacb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727089"
---
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="43c4f-102">Tipo definido por el usuario DecodeOp</span><span class="sxs-lookup"><span data-stu-id="43c4f-102">DecodeOp user defined type</span></span>

<span data-ttu-id="43c4f-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="43c4f-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="43c4f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43c4f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43c4f-105">Representa una operación que descodifica un registro codificado en un registro físico y el qubits temporal que se usa para registrar un síndrome.</span><span class="sxs-lookup"><span data-stu-id="43c4f-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="43c4f-106">El argumento para un DecodeOp es el mismo que el valor devuelto de un EncodeOp y viceversa.</span><span class="sxs-lookup"><span data-stu-id="43c4f-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

