---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 5d50b3fdc2b0f948e93cb11b5c69403d97574ccd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843954"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="420c9-102">RotationPhasesAsReflectionPhases función)</span><span class="sxs-lookup"><span data-stu-id="420c9-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="420c9-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="420c9-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="420c9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="420c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="420c9-105">Convierte las fases especificadas como rotaciones de un solo qubit en fases especificadas como reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="420c9-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="420c9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="420c9-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="420c9-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="420c9-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="420c9-108">Matriz de rotaciones de un solo qubit que se van a convertir en reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="420c9-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="420c9-109">Salida: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="420c9-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="420c9-110">Operación que implementa las fases especificadas como reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="420c9-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="420c9-111">Referencias</span><span class="sxs-lookup"><span data-stu-id="420c9-111">References</span></span>

<span data-ttu-id="420c9-112">Usamos la Convención en</span><span class="sxs-lookup"><span data-stu-id="420c9-112">We use the convention in</span></span>

- <span data-ttu-id="420c9-113">[ *G.H. Low, i. L. Chuang*](https://arxiv.org/abs/1707.05391) para relacionar las fases de rotación de un solo qubit con las fases del operador de reflexión.</span><span class="sxs-lookup"><span data-stu-id="420c9-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>