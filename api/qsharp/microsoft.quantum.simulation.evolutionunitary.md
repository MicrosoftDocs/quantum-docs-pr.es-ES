---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: Tipo definido por el usuario EvolutionUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 28ab492573b67e4aa42392e4ee499596b9c0225f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733708"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="46bb3-102">Tipo definido por el usuario EvolutionUnitary</span><span class="sxs-lookup"><span data-stu-id="46bb3-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="46bb3-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="46bb3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="46bb3-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="46bb3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="46bb3-105">Representa un operador de evolución de tiempo unitario.</span><span class="sxs-lookup"><span data-stu-id="46bb3-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="46bb3-106">El primer parámetro es la duración de la evolución del tiempo y el segundo parámetro es el registro de qubit sobre el que actúa la unitario.</span><span class="sxs-lookup"><span data-stu-id="46bb3-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

