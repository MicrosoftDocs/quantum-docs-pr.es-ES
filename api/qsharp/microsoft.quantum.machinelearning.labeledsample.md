---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definido por el usuario LabeledSample
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196334"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="6222d-102">Tipo definido por el usuario LabeledSample</span><span class="sxs-lookup"><span data-stu-id="6222d-102">LabeledSample user defined type</span></span>

<span data-ttu-id="6222d-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6222d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6222d-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6222d-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="6222d-105">Un ejemplo, etiquetado con una clase a la que pertenece el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6222d-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="6222d-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="6222d-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="6222d-107">Características: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6222d-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6222d-108">Vector de características para el ejemplo especificado.</span><span class="sxs-lookup"><span data-stu-id="6222d-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="6222d-109">Etiqueta: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6222d-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6222d-110">Una etiqueta de entero para la clase a la que pertenece este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6222d-110">An integer label for the class to which this sample belongs.</span></span>