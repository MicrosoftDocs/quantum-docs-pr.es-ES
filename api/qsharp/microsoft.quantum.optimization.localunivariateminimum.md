---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854604"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="fcd4e-102">LocalUnivariateMinimum función)</span><span class="sxs-lookup"><span data-stu-id="fcd4e-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="fcd4e-103">Espacio de nombres: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="fcd4e-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="fcd4e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fcd4e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fcd4e-105">Devuelve el mínimo local para una función univariante sobre un intervalo delimitado, mediante una búsqueda de intervalo de Golden.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="fcd4e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fcd4e-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="fcd4e-107">FN: [doble](xref:microsoft.quantum.lang-ref.double) -> [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fcd4e-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fcd4e-108">La función univariante que se va a minimizar.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="fcd4e-109">Bounds: ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="fcd4e-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="fcd4e-110">El intervalo en el que se debe encontrar el mínimo local.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="fcd4e-111">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fcd4e-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fcd4e-112">Precisión en la entrada de la función que se va a tolerar.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="fcd4e-113">La búsqueda del local optima continuará hasta que el intervalo tenga un ancho inferior al de esta tolerancia.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="fcd4e-114">Salida: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="fcd4e-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="fcd4e-115">Un local optima de la función especificada, que se encuentra dentro de los límites especificados.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-115">A local optima of the given function, located within the given bounds.</span></span>