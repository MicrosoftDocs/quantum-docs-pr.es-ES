---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Tipo definido por el usuario ReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: 743ece778239c223573a3a8536ae8059cea09d5f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191353"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="661ed-102">Tipo definido por el usuario ReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="661ed-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="661ed-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="661ed-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="661ed-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="661ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="661ed-105">Fases para una secuencia de reflejos parciales en amplificación de amplitud.</span><span class="sxs-lookup"><span data-stu-id="661ed-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="661ed-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="661ed-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="661ed-107">AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="661ed-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="661ed-108">Una matriz de fases para la reflexión sobre el estado de inicio.</span><span class="sxs-lookup"><span data-stu-id="661ed-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="661ed-109">AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="661ed-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="661ed-110">Una matriz de fases para la reflexión sobre el estado de destino.</span><span class="sxs-lookup"><span data-stu-id="661ed-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="661ed-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="661ed-111">Remarks</span></span>

<span data-ttu-id="661ed-112">Ambas matrices deben tener la misma longitud.</span><span class="sxs-lookup"><span data-stu-id="661ed-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="661ed-113">Tenga en cuenta que, en muchos casos, la primera fase sobre el estado de inicio y la última fase sobre el estado de destino introduce un cambio de fase global y se puede establecer en $0 $.</span><span class="sxs-lookup"><span data-stu-id="661ed-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>