---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definido por el usuario LabeledSample
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726627"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="dac2a-102">Tipo definido por el usuario LabeledSample</span><span class="sxs-lookup"><span data-stu-id="dac2a-102">LabeledSample user defined type</span></span>

<span data-ttu-id="dac2a-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dac2a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="dac2a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dac2a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dac2a-105">Un ejemplo, etiquetado con una clase a la que pertenece el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dac2a-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="dac2a-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="dac2a-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="dac2a-107">Características: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="dac2a-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="dac2a-108">Vector de características para el ejemplo especificado.</span><span class="sxs-lookup"><span data-stu-id="dac2a-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="dac2a-109">Etiqueta: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dac2a-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dac2a-110">Una etiqueta de entero para la clase a la que pertenece este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dac2a-110">An integer label for the class to which this sample belongs.</span></span>