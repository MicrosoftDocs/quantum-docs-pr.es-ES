---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operación GetQubitsAvailableToBorrow
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727166"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="12352-102">Operación GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="12352-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="12352-103">Espacio de nombres: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="12352-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="12352-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="12352-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="12352-105">Devuelve el número de qubits disponibles actualmente para tomar prestado.</span><span class="sxs-lookup"><span data-stu-id="12352-105">Returns the number of qubits currently available to borrow.</span></span>
<span data-ttu-id="12352-106">Esto incluye qubits sin usar; es decir, esto incluye el qubits devuelto por `GetQubitsAvailableToUse` .</span><span class="sxs-lookup"><span data-stu-id="12352-106">This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="12352-107">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="12352-107">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="12352-108">El número de qubits que se pueden asignar en una `borrowing` instrucción.</span><span class="sxs-lookup"><span data-stu-id="12352-108">The number of qubits that could be allocated in a `borrowing` statement.</span></span>
<span data-ttu-id="12352-109">Si el equipo de destino que se usa no proporciona esta información, `-1` se devuelve.</span><span class="sxs-lookup"><span data-stu-id="12352-109">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="12352-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12352-110">See Also</span></span>

- [<span data-ttu-id="12352-111">Microsoft. Quantum. Environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="12352-111">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)