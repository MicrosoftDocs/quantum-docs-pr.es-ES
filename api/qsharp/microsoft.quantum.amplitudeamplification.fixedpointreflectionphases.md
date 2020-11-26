---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 8cc1073447f5fae87ece38db64dcc312f6208899
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191455"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="81e39-102">FixedPointReflectionPhases función)</span><span class="sxs-lookup"><span data-stu-id="81e39-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="81e39-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="81e39-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="81e39-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="81e39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="81e39-105">Calcula las fases de reflexión parcial para la amplificación de amplitud de punto fijo.</span><span class="sxs-lookup"><span data-stu-id="81e39-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="81e39-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="81e39-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="81e39-107">nQueries: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="81e39-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="81e39-108">Número de consultas a la preparación de estado de Oracle.</span><span class="sxs-lookup"><span data-stu-id="81e39-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="81e39-109">Debe ser un entero impar.</span><span class="sxs-lookup"><span data-stu-id="81e39-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="81e39-110">successMin: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81e39-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="81e39-111">Probabilidad de éxito mínima de destino.</span><span class="sxs-lookup"><span data-stu-id="81e39-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="81e39-112">Salida: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="81e39-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="81e39-113">Matriz de fases que se puede usar en la implementación del algoritmo Quantum de amplificación de amplitud de punto fijo.</span><span class="sxs-lookup"><span data-stu-id="81e39-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="81e39-114">Referencias</span><span class="sxs-lookup"><span data-stu-id="81e39-114">References</span></span>

<span data-ttu-id="81e39-115">Usamos las fases de la amplificación de amplitud de puntos fijos con un número óptimo de consultas.</span><span class="sxs-lookup"><span data-stu-id="81e39-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="81e39-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Vea también "metodología de las puertas de Quantum compuestas"</span><span class="sxs-lookup"><span data-stu-id="81e39-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="81e39-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) para las fases en el `RotationPhases` formato.</span><span class="sxs-lookup"><span data-stu-id="81e39-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>