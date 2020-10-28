---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: d62a7584324c9467ccc759e4bed81acbceee719c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731933"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="40a2e-102">RotationPhasesAsReflectionPhases función)</span><span class="sxs-lookup"><span data-stu-id="40a2e-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="40a2e-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="40a2e-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="40a2e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="40a2e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="40a2e-105">Convierte las fases especificadas como rotaciones de un solo qubit en fases especificadas como reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="40a2e-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="40a2e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="40a2e-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="40a2e-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="40a2e-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="40a2e-108">Matriz de rotaciones de un solo qubit que se van a convertir en reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="40a2e-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="40a2e-109">Salida: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="40a2e-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="40a2e-110">Operación que implementa las fases especificadas como reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="40a2e-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="40a2e-111">Referencias</span><span class="sxs-lookup"><span data-stu-id="40a2e-111">References</span></span>

<span data-ttu-id="40a2e-112">Usamos la Convención en</span><span class="sxs-lookup"><span data-stu-id="40a2e-112">We use the convention in</span></span>

- <span data-ttu-id="40a2e-113">[ *G.H. Low, i. L. Chuang*](https://arxiv.org/abs/1707.05391) para relacionar las fases de rotación de un solo qubit con las fases del operador de reflexión.</span><span class="sxs-lookup"><span data-stu-id="40a2e-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>