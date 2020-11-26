---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: Tipo definido por el usuario EvolutionUnitary
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 38e7da28d4146df9cc132ad69ee939c44bc917f7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225268"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="a39c6-102">Tipo definido por el usuario EvolutionUnitary</span><span class="sxs-lookup"><span data-stu-id="a39c6-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="a39c6-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a39c6-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a39c6-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a39c6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a39c6-105">Representa un operador de evolución de tiempo unitario.</span><span class="sxs-lookup"><span data-stu-id="a39c6-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="a39c6-106">El primer parámetro es la duración de la evolución del tiempo y el segundo parámetro es el registro de qubit sobre el que actúa la unitario.</span><span class="sxs-lookup"><span data-stu-id="a39c6-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

