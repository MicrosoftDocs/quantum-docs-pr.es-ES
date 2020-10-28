---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Tipo definido por el usuario RotationPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731941"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="e2469-102">Tipo definido por el usuario RotationPhases</span><span class="sxs-lookup"><span data-stu-id="e2469-102">RotationPhases user defined type</span></span>

<span data-ttu-id="e2469-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e2469-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e2469-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e2469-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e2469-105">Fases para una secuencia de rotaciones de un solo qubit en amplificación de amplitud.</span><span class="sxs-lookup"><span data-stu-id="e2469-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="e2469-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e2469-106">Remarks</span></span>

<span data-ttu-id="e2469-107">El primer parámetro es una matriz de fases para las reflexiones, expresadas como un producto de rotaciones de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="e2469-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="e2469-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="e2469-108">[ G.H.</span></span> <span data-ttu-id="e2469-109">Bajo, I. L.</span><span class="sxs-lookup"><span data-stu-id="e2469-109">Low, I. L.</span></span> <span data-ttu-id="e2469-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="e2469-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>