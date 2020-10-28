---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Tipo definido por el usuario UnivariateOptimizationResult
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733404"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="c57a3-102">Tipo definido por el usuario UnivariateOptimizationResult</span><span class="sxs-lookup"><span data-stu-id="c57a3-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="c57a3-103">Espacio de nombres: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="c57a3-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="c57a3-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c57a3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c57a3-105">Representa el resultado de la optimización de una función univariante.</span><span class="sxs-lookup"><span data-stu-id="c57a3-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="c57a3-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="c57a3-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="c57a3-107">Coordenada: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c57a3-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c57a3-108">Entrada en la que se encontró un óptimo.</span><span class="sxs-lookup"><span data-stu-id="c57a3-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="c57a3-109">Valor: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c57a3-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c57a3-110">Valor devuelto por la función de forma óptima.</span><span class="sxs-lookup"><span data-stu-id="c57a3-110">Value returned by the function at its optimum.</span></span>