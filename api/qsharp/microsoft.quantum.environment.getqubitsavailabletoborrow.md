---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operación GetQubitsAvailableToBorrow
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: 30b97c2b6e1353f008d085c3bae6160763557c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201468"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="01bfe-102">Operación GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="01bfe-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="01bfe-103">Espacio de nombres: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="01bfe-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="01bfe-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="01bfe-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="01bfe-105">Devuelve el número de qubits disponibles actualmente para tomar prestado.</span><span class="sxs-lookup"><span data-stu-id="01bfe-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="01bfe-106">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01bfe-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01bfe-107">El número de qubits que se podrían tomar prestado y no se asignarán como parte de una `borrowing` instrucción.</span><span class="sxs-lookup"><span data-stu-id="01bfe-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="01bfe-108">Si el equipo de destino que se usa no proporciona esta información, `-1` se devuelve.</span><span class="sxs-lookup"><span data-stu-id="01bfe-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="01bfe-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01bfe-109">See Also</span></span>

- [<span data-ttu-id="01bfe-110">Microsoft. Quantum. Environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="01bfe-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)