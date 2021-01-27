---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Función muestreada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854943"
---
# <a name="sampled-function"></a><span data-ttu-id="64216-102">Función muestreada</span><span class="sxs-lookup"><span data-stu-id="64216-102">Sampled function</span></span>

<span data-ttu-id="64216-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="64216-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="64216-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="64216-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="64216-105">Muestrea una matriz determinada, usando la programación especificada.</span><span class="sxs-lookup"><span data-stu-id="64216-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="64216-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="64216-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="64216-107">Programación: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="64216-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="64216-108">Una programación que se va a usar en los valores de muestreo.</span><span class="sxs-lookup"><span data-stu-id="64216-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="64216-109">valores: ' t []</span><span class="sxs-lookup"><span data-stu-id="64216-109">values : 'T[]</span></span>

<span data-ttu-id="64216-110">Matriz de valores que se van a muestrear.</span><span class="sxs-lookup"><span data-stu-id="64216-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="64216-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="64216-111">Output : 'T[]</span></span>

<span data-ttu-id="64216-112">Matriz de elementos a partir de valores, siguiendo la programación especificada.</span><span class="sxs-lookup"><span data-stu-id="64216-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="64216-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="64216-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="64216-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="64216-114">'T</span></span>

