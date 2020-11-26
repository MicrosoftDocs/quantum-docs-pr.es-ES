---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Operación MaybeChooseElement
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192866"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="e051c-102">Operación MaybeChooseElement</span><span class="sxs-lookup"><span data-stu-id="e051c-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="e051c-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="e051c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="e051c-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e051c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e051c-105">Dada una matriz de datos y una distribución a través de sus índices, intenta elegir un elemento de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="e051c-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="e051c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e051c-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="e051c-107">datos: ' t []</span><span class="sxs-lookup"><span data-stu-id="e051c-107">data : 'T[]</span></span>

<span data-ttu-id="e051c-108">Matriz de la que se debe elegir un elemento.</span><span class="sxs-lookup"><span data-stu-id="e051c-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="e051c-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="e051c-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="e051c-110">Una distribución a través de los índices de `data` .</span><span class="sxs-lookup"><span data-stu-id="e051c-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="e051c-111">Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t)</span><span class="sxs-lookup"><span data-stu-id="e051c-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e051c-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="e051c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e051c-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="e051c-113">'T</span></span>

