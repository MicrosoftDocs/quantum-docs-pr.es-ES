---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: Tipo definido por el usuario EncodeOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: da947cdc25cb0edd3a4144022bbfc6ecb84c647f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727064"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="58cd1-102">Tipo definido por el usuario EncodeOp</span><span class="sxs-lookup"><span data-stu-id="58cd1-102">EncodeOp user defined type</span></span>

<span data-ttu-id="58cd1-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="58cd1-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="58cd1-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58cd1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="58cd1-105">Representa una operación que codifica un registro físico en un registro lógico, utilizando el qubits temporal proporcionado.</span><span class="sxs-lookup"><span data-stu-id="58cd1-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="58cd1-106">El primer argumento se toma como el registro físico que se va a codificar, mientras que el segundo argumento se toma como el registro temporal que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="58cd1-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

