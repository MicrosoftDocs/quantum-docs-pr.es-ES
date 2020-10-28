---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Tipo definido por el usuario SyndromeMeasOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726963"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="16f59-102">Tipo definido por el usuario SyndromeMeasOp</span><span class="sxs-lookup"><span data-stu-id="16f59-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="16f59-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="16f59-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="16f59-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="16f59-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="16f59-105">Representa una operación que se utiliza para medir el síndrome de un bloque de código de corrección de errores.</span><span class="sxs-lookup"><span data-stu-id="16f59-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="16f59-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="16f59-106">Remarks</span></span>

<span data-ttu-id="16f59-107">La firma `(LogicalRegister => Syndrome)` representa una operación que actúa conjuntamente en el qubits en `LogicalRegister` y algunos qubits auxiliares seguidos de una medida de la qubits auxiliar para extraer un `Syndrome` valor que representa el `Result[]` de estas medidas.</span><span class="sxs-lookup"><span data-stu-id="16f59-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="16f59-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="16f59-108">See Also</span></span>

- [<span data-ttu-id="16f59-109">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="16f59-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="16f59-110">Microsoft. Quantum. ErrorCorrection. síndrome</span><span class="sxs-lookup"><span data-stu-id="16f59-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)