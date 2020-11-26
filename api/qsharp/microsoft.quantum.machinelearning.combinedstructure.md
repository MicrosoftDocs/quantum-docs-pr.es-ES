---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: 0a7d66be8b45d6a9df95b425e66b9b6bba241136
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211974"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="a3ed8-102">CombinedStructure función)</span><span class="sxs-lookup"><span data-stu-id="a3ed8-102">CombinedStructure function</span></span>

<span data-ttu-id="a3ed8-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a3ed8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a3ed8-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a3ed8-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a3ed8-105">Dado una o más capas de rotaciones controladas, devuelve una sola capa con el índice del parámetro de modelo desplazado de modo que las capas distintas estén parametrizadas por parámetros de modelo distintos.</span><span class="sxs-lookup"><span data-stu-id="a3ed8-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="a3ed8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a3ed8-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="a3ed8-107">capas: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="a3ed8-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="a3ed8-108">Capas que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="a3ed8-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="a3ed8-109">Salida: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="a3ed8-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="a3ed8-110">Una sola capa de giros controlados que representa la concatenación de todas las demás capas.</span><span class="sxs-lookup"><span data-stu-id="a3ed8-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>