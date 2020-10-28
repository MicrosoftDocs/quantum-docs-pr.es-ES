---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Función muestreada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732317"
---
# <a name="sampled-function"></a><span data-ttu-id="212a9-102">Función muestreada</span><span class="sxs-lookup"><span data-stu-id="212a9-102">Sampled function</span></span>

<span data-ttu-id="212a9-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="212a9-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="212a9-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="212a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="212a9-105">Muestrea una matriz determinada, usando la programación especificada.</span><span class="sxs-lookup"><span data-stu-id="212a9-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="212a9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="212a9-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="212a9-107">Programación: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="212a9-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="212a9-108">Una programación que se va a usar en los valores de muestreo.</span><span class="sxs-lookup"><span data-stu-id="212a9-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="212a9-109">valores: ' t []</span><span class="sxs-lookup"><span data-stu-id="212a9-109">values : 'T[]</span></span>

<span data-ttu-id="212a9-110">Matriz de valores que se van a muestrear.</span><span class="sxs-lookup"><span data-stu-id="212a9-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="212a9-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="212a9-111">Output : 'T[]</span></span>

<span data-ttu-id="212a9-112">Matriz de elementos a partir de valores, siguiendo la programación especificada.</span><span class="sxs-lookup"><span data-stu-id="212a9-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="212a9-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="212a9-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="212a9-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="212a9-114">'T</span></span>

