---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Operación MaybeChooseElement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732172"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="2beed-102">Operación MaybeChooseElement</span><span class="sxs-lookup"><span data-stu-id="2beed-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="2beed-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="2beed-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="2beed-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2beed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2beed-105">Dada una matriz de datos y una distribución a través de sus índices, intenta elegir un elemento de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="2beed-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="2beed-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2beed-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="2beed-107">datos: ' t []</span><span class="sxs-lookup"><span data-stu-id="2beed-107">data : 'T[]</span></span>

<span data-ttu-id="2beed-108">Matriz de la que se debe elegir un elemento.</span><span class="sxs-lookup"><span data-stu-id="2beed-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="2beed-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="2beed-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="2beed-110">Una distribución a través de los índices de `data` .</span><span class="sxs-lookup"><span data-stu-id="2beed-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="2beed-111">Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t)</span><span class="sxs-lookup"><span data-stu-id="2beed-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2beed-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2beed-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2beed-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="2beed-113">'T</span></span>

