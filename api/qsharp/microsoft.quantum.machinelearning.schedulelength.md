---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: dd042b1282d2f5386ee0b67bf57ad4027eefd493
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854905"
---
# <a name="schedulelength-function"></a><span data-ttu-id="854db-102">ScheduleLength función)</span><span class="sxs-lookup"><span data-stu-id="854db-102">ScheduleLength function</span></span>

<span data-ttu-id="854db-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="854db-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="854db-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="854db-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="854db-105">Devuelve el número de elementos de una programación de muestreo determinada.</span><span class="sxs-lookup"><span data-stu-id="854db-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="854db-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="854db-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="854db-107">Programación: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="854db-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="854db-108">Programación de muestreo cuya longitud se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="854db-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="854db-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="854db-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="854db-110">Número de elementos de la programación de muestreo dada.</span><span class="sxs-lookup"><span data-stu-id="854db-110">The number of elements in the given sampling schedule.</span></span>