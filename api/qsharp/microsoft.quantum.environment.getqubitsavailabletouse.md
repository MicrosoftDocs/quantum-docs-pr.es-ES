---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operación GetQubitsAvailableToUse
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201417"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="7d0c4-102">Operación GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="7d0c4-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="7d0c4-103">Espacio de nombres: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="7d0c4-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="7d0c4-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7d0c4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7d0c4-105">Devuelve el número de qubits disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="7d0c4-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="7d0c4-106">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7d0c4-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7d0c4-107">El número de qubits que se pueden asignar en una `using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7d0c4-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="7d0c4-108">Si el equipo de destino que se usa no proporciona esta información, `-1` se devuelve.</span><span class="sxs-lookup"><span data-stu-id="7d0c4-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d0c4-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d0c4-109">See Also</span></span>

- [<span data-ttu-id="7d0c4-110">Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="7d0c4-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)