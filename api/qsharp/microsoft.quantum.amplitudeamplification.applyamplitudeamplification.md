---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: Operación ApplyAmplitudeAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: be884eab70c7f72f994baf6bd7caf05769e0d5f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732036"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="8a62b-102">Operación ApplyAmplitudeAmplification</span><span class="sxs-lookup"><span data-stu-id="8a62b-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="8a62b-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="8a62b-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="8a62b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a62b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a62b-105">Aplica amplificación de amplitud en un registro determinado, utilizando un conjunto determinado de fases y Oracle para reflejar los Estados inicial y final.</span><span class="sxs-lookup"><span data-stu-id="8a62b-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8a62b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8a62b-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="8a62b-107">fases: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="8a62b-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="8a62b-108">Un conjunto de fases que describen las reflexiones parciales en cada paso del algoritmo de amplificación de amplitud.</span><span class="sxs-lookup"><span data-stu-id="8a62b-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="8a62b-109">Vea @"microsoft.quantum.amplitudeamplification.standardreflectionphases" para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8a62b-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="8a62b-110">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="8a62b-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="8a62b-111">Oracle que refleja el estado inicial.</span><span class="sxs-lookup"><span data-stu-id="8a62b-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="8a62b-112">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="8a62b-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="8a62b-113">Oracle que refleja el estado final deseado.</span><span class="sxs-lookup"><span data-stu-id="8a62b-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8a62b-114">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8a62b-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8a62b-115">Un registro para realizar la amplificación de amplitud en.</span><span class="sxs-lookup"><span data-stu-id="8a62b-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8a62b-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a62b-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

