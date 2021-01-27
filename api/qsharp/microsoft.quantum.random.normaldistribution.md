---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814184"
---
# <a name="normaldistribution-function"></a><span data-ttu-id="c8f8c-102">NormalDistribution función)</span><span class="sxs-lookup"><span data-stu-id="c8f8c-102">NormalDistribution function</span></span>

<span data-ttu-id="c8f8c-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c8f8c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c8f8c-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c8f8c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c8f8c-105">Devuelve una distribución normal con una media y una varianza determinadas.</span><span class="sxs-lookup"><span data-stu-id="c8f8c-105">Returns a normal distribution with a given mean and variance.</span></span>

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="c8f8c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c8f8c-106">Input</span></span>

### <a name="mean--double"></a><span data-ttu-id="c8f8c-107">promedio: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c8f8c-107">mean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="variance--double"></a><span data-ttu-id="c8f8c-108">varianza: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c8f8c-108">variance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--continuousdistribution"></a><span data-ttu-id="c8f8c-109">Salida: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="c8f8c-109">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="c8f8c-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8f8c-110">Example</span></span>

<span data-ttu-id="c8f8c-111">En el siguiente ejemplo se dibujan 10 ejemplos de la distribución normal con la media 2 y la desviación estándar 0,1:</span><span class="sxs-lookup"><span data-stu-id="c8f8c-111">The following draws 10 samples from the normal distribution with mean 2 and standard deviation 0.1:</span></span>

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a><span data-ttu-id="c8f8c-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8f8c-112">See Also</span></span>

- [<span data-ttu-id="c8f8c-113">Microsoft. Quantum. random. StandardNormalDistribution</span><span class="sxs-lookup"><span data-stu-id="c8f8c-113">Microsoft.Quantum.Random.StandardNormalDistribution</span></span>](xref:Microsoft.Quantum.Random.StandardNormalDistribution)