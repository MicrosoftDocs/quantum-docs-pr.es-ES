---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definido por el usuario LabeledSample
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846974"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="a1284-102">Tipo definido por el usuario LabeledSample</span><span class="sxs-lookup"><span data-stu-id="a1284-102">LabeledSample user defined type</span></span>

<span data-ttu-id="a1284-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a1284-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a1284-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a1284-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a1284-105">Un ejemplo, etiquetado con una clase a la que pertenece el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a1284-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="a1284-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="a1284-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="a1284-107">Características: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a1284-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a1284-108">Vector de características para el ejemplo especificado.</span><span class="sxs-lookup"><span data-stu-id="a1284-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="a1284-109">Etiqueta: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a1284-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a1284-110">Una etiqueta de entero para la clase a la que pertenece este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a1284-110">An integer label for the class to which this sample belongs.</span></span>