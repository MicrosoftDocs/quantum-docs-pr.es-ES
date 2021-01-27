---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 703b50d0186cd0f4eddb9a29fa3cffb2b746c8d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843910"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="39e20-102">StandardReflectionPhases función)</span><span class="sxs-lookup"><span data-stu-id="39e20-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="39e20-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="39e20-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="39e20-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39e20-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39e20-105">Calcula las fases de reflexión parcial para la amplificación de amplitud estándar.</span><span class="sxs-lookup"><span data-stu-id="39e20-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="39e20-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="39e20-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="39e20-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39e20-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39e20-108">Número de iteraciones de amplificación de amplitud para las que generar fases de reflexión parcial.</span><span class="sxs-lookup"><span data-stu-id="39e20-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="39e20-109">Salida: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="39e20-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="39e20-110">Operación que implementa las fases especificadas como reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="39e20-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="39e20-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="39e20-111">Remarks</span></span>

<span data-ttu-id="39e20-112">Todas las fases son $ \pi $, excepto la primera reflexión sobre el estado de inicio y la última reflexión sobre el estado de destino, que son $0 $.</span><span class="sxs-lookup"><span data-stu-id="39e20-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>