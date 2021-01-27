---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: Tipo definido por el usuario SimulationAlgorithm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: d7b233ee76d79072f59ecfd001245848cb780eec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851040"
---
# <a name="simulationalgorithm-user-defined-type"></a><span data-ttu-id="38ec0-102">Tipo definido por el usuario SimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="38ec0-102">SimulationAlgorithm user defined type</span></span>

<span data-ttu-id="38ec0-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="38ec0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="38ec0-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38ec0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38ec0-105">Representa un algoritmo de simulación independiente del tiempo.</span><span class="sxs-lookup"><span data-stu-id="38ec0-105">Represents a time-independent simulation algorithm.</span></span>

<span data-ttu-id="38ec0-106">Una técnica de simulación independiente del tiempo convierte un <xref:microsoft.quantum.simulation.evolutiongenerator></span><span class="sxs-lookup"><span data-stu-id="38ec0-106">A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator></span></span>
<span data-ttu-id="38ec0-107">para obtener la evolución de la hora en un intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="38ec0-107">to unitary time evolution for some time-interval.</span></span>

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```

