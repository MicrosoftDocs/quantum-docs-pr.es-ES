---
uid: Microsoft.Quantum.Simulation.Unitary
title: Tipo definido por el usuario unitario
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: d2bba42e80132d0879f42922f28ad50bef54edf3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733980"
---
# <a name="unitary-user-defined-type"></a><span data-ttu-id="4ca6d-102">Tipo definido por el usuario unitario</span><span class="sxs-lookup"><span data-stu-id="4ca6d-102">Unitary user defined type</span></span>

<span data-ttu-id="4ca6d-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4ca6d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4ca6d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4ca6d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4ca6d-105">Representa la evolución en un operador unitario.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-105">Represents evolution under a unitary operator.</span></span>

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```
