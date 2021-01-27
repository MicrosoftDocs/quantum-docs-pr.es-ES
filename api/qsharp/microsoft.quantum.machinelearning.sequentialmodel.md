---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Tipo definido por el usuario SequentialModel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854895"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="3e4c7-102">Tipo definido por el usuario SequentialModel</span><span class="sxs-lookup"><span data-stu-id="3e4c7-102">SequentialModel user defined type</span></span>

<span data-ttu-id="3e4c7-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3e4c7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3e4c7-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3e4c7-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="3e4c7-105">Describe un modelo de clasificador de Quantum compuesto por una secuencia de giros con parámetros y controlados, una asignación de ángulos de rotación y una diferencia entre las dos clases reconocidas por el modelo.</span><span class="sxs-lookup"><span data-stu-id="3e4c7-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="3e4c7-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="3e4c7-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="3e4c7-107">Estructura: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="3e4c7-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="3e4c7-108">Secuencia de las rotaciones controladas utilizadas para clasificar las entradas.</span><span class="sxs-lookup"><span data-stu-id="3e4c7-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="3e4c7-109">Parámetros: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3e4c7-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3e4c7-110">Asignación de ángulos de rotación a la estructura de clasificación indicada.</span><span class="sxs-lookup"><span data-stu-id="3e4c7-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="3e4c7-111">Bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3e4c7-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3e4c7-112">La diferencia entre las dos clases reconocidas por este clasificador.</span><span class="sxs-lookup"><span data-stu-id="3e4c7-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="3e4c7-113">Referencias</span><span class="sxs-lookup"><span data-stu-id="3e4c7-113">References</span></span>

- [<span data-ttu-id="3e4c7-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="3e4c7-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)