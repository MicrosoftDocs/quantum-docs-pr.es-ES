---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Tipo definido por el usuario UnivariateOptimizationResult
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194039"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="a5fed-102">Tipo definido por el usuario UnivariateOptimizationResult</span><span class="sxs-lookup"><span data-stu-id="a5fed-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="a5fed-103">Espacio de nombres: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="a5fed-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="a5fed-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a5fed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a5fed-105">Representa el resultado de la optimización de una función univariante.</span><span class="sxs-lookup"><span data-stu-id="a5fed-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="a5fed-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="a5fed-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="a5fed-107">Coordenada: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a5fed-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a5fed-108">Entrada en la que se encontró un óptimo.</span><span class="sxs-lookup"><span data-stu-id="a5fed-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="a5fed-109">Valor: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a5fed-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a5fed-110">Valor devuelto por la función de forma óptima.</span><span class="sxs-lookup"><span data-stu-id="a5fed-110">Value returned by the function at its optimum.</span></span>