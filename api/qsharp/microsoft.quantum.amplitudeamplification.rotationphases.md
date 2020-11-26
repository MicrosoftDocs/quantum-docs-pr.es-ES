---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Tipo definido por el usuario RotationPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191370"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="5e04b-102">Tipo definido por el usuario RotationPhases</span><span class="sxs-lookup"><span data-stu-id="5e04b-102">RotationPhases user defined type</span></span>

<span data-ttu-id="5e04b-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="5e04b-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="5e04b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e04b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e04b-105">Fases para una secuencia de rotaciones de un solo qubit en amplificación de amplitud.</span><span class="sxs-lookup"><span data-stu-id="5e04b-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="5e04b-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5e04b-106">Remarks</span></span>

<span data-ttu-id="5e04b-107">El primer parámetro es una matriz de fases para las reflexiones, expresadas como un producto de rotaciones de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="5e04b-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="5e04b-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="5e04b-108">[ G.H.</span></span> <span data-ttu-id="5e04b-109">Bajo, I. L.</span><span class="sxs-lookup"><span data-stu-id="5e04b-109">Low, I. L.</span></span> <span data-ttu-id="5e04b-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="5e04b-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>