---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Tipo definido por el usuario SequentialModel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732300"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="89886-102">Tipo definido por el usuario SequentialModel</span><span class="sxs-lookup"><span data-stu-id="89886-102">SequentialModel user defined type</span></span>

<span data-ttu-id="89886-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="89886-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="89886-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89886-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="89886-105">Describe un modelo de clasificador de Quantum compuesto por una secuencia de giros con parámetros y controlados, una asignación de ángulos de rotación y una diferencia entre las dos clases reconocidas por el modelo.</span><span class="sxs-lookup"><span data-stu-id="89886-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="89886-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="89886-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="89886-107">Estructura: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="89886-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="89886-108">Secuencia de las rotaciones controladas utilizadas para clasificar las entradas.</span><span class="sxs-lookup"><span data-stu-id="89886-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="89886-109">Parámetros: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="89886-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="89886-110">Asignación de ángulos de rotación a la estructura de clasificación indicada.</span><span class="sxs-lookup"><span data-stu-id="89886-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="89886-111">Bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="89886-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="89886-112">La diferencia entre las dos clases reconocidas por este clasificador.</span><span class="sxs-lookup"><span data-stu-id="89886-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="89886-113">Referencias</span><span class="sxs-lookup"><span data-stu-id="89886-113">References</span></span>

- [<span data-ttu-id="89886-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="89886-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)