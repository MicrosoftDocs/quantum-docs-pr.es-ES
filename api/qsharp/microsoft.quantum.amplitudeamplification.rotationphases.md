---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Tipo definido por el usuario RotationPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843960"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="6205c-102">Tipo definido por el usuario RotationPhases</span><span class="sxs-lookup"><span data-stu-id="6205c-102">RotationPhases user defined type</span></span>

<span data-ttu-id="6205c-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="6205c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="6205c-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6205c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6205c-105">Fases para una secuencia de rotaciones de un solo qubit en amplificación de amplitud.</span><span class="sxs-lookup"><span data-stu-id="6205c-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="6205c-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6205c-106">Remarks</span></span>

<span data-ttu-id="6205c-107">El primer parámetro es una matriz de fases para las reflexiones, expresadas como un producto de rotaciones de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="6205c-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="6205c-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="6205c-108">[ G.H.</span></span> <span data-ttu-id="6205c-109">Bajo, I. L.</span><span class="sxs-lookup"><span data-stu-id="6205c-109">Low, I. L.</span></span> <span data-ttu-id="6205c-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="6205c-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>