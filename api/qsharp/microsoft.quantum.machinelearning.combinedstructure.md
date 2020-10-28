---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731116"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="38b55-102">CombinedStructure función)</span><span class="sxs-lookup"><span data-stu-id="38b55-102">CombinedStructure function</span></span>

<span data-ttu-id="38b55-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="38b55-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="38b55-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="38b55-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="38b55-105">Dado una o más capas de rotaciones controladas, devuelve una sola capa con el índice del parámetro de modelo desplazado de modo que las capas distintas estén parametrizadas por parámetros de modelo distintos.</span><span class="sxs-lookup"><span data-stu-id="38b55-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="38b55-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="38b55-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="38b55-107">capas: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="38b55-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="38b55-108">Capas que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="38b55-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="38b55-109">Salida: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="38b55-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="38b55-110">Una sola capa de giros controlados que representa la concatenación de todas las demás capas.</span><span class="sxs-lookup"><span data-stu-id="38b55-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>