---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operación GetQubitsAvailableToUse
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727161"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="b7499-102">Operación GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="b7499-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="b7499-103">Espacio de nombres: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="b7499-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="b7499-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7499-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7499-105">Devuelve el número de qubits disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="b7499-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="b7499-106">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b7499-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b7499-107">El número de qubits que se pueden asignar en una `using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b7499-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="b7499-108">Si el equipo de destino que se usa no proporciona esta información, `-1` se devuelve.</span><span class="sxs-lookup"><span data-stu-id="b7499-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7499-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7499-109">See Also</span></span>

- [<span data-ttu-id="b7499-110">Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="b7499-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)