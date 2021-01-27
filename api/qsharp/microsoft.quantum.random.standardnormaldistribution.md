---
uid: Microsoft.Quantum.Random.StandardNormalDistribution
title: StandardNormalDistribution función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: StandardNormalDistribution
qsharp.summary: Returns a normal distribution with mean 0 and variance 1.
ms.openlocfilehash: e1776339655c33516f7b3d156f1b377a0c74d250
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857809"
---
# <a name="standardnormaldistribution-function"></a><span data-ttu-id="3da4c-102">StandardNormalDistribution función)</span><span class="sxs-lookup"><span data-stu-id="3da4c-102">StandardNormalDistribution function</span></span>

<span data-ttu-id="3da4c-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3da4c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3da4c-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3da4c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3da4c-105">Devuelve una distribución normal con una media de 0 y una varianza de 1.</span><span class="sxs-lookup"><span data-stu-id="3da4c-105">Returns a normal distribution with mean 0 and variance 1.</span></span>

```qsharp
function StandardNormalDistribution () : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="output--continuousdistribution"></a><span data-ttu-id="3da4c-106">Salida: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="3da4c-106">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="3da4c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3da4c-107">Example</span></span>

<span data-ttu-id="3da4c-108">En el siguiente ejemplo se dibujan 10 ejemplos de la distribución normal estándar:</span><span class="sxs-lookup"><span data-stu-id="3da4c-108">The following draws 10 samples from the standard normal distribution:</span></span>

```qsharp
let samples = DrawMany((StandardNormalDistribution())::Sample, 10, ());
```

## <a name="see-also"></a><span data-ttu-id="3da4c-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3da4c-109">See Also</span></span>

- [<span data-ttu-id="3da4c-110">Microsoft. Quantum. random. NormalDistribution</span><span class="sxs-lookup"><span data-stu-id="3da4c-110">Microsoft.Quantum.Random.NormalDistribution</span></span>](xref:Microsoft.Quantum.Random.NormalDistribution)