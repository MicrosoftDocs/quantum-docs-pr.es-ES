---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 035c353c34362aa3486a7df9e7bb1bc95a6f63be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856175"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="baaa8-102">ApproximateInputEncoder función)</span><span class="sxs-lookup"><span data-stu-id="baaa8-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="baaa8-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="baaa8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="baaa8-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="baaa8-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="baaa8-105">Dado un conjunto de coeficientes y una tolerancia, devuelve una operación de preparación del estado que prepara cada coeficiente como la amplitud correspondiente del estado de la base de cálculo, hasta la tolerancia especificada.</span><span class="sxs-lookup"><span data-stu-id="baaa8-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="baaa8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="baaa8-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="baaa8-107">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="baaa8-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="baaa8-108">Tolerancia de aproximación que se va a usar para codificar los coeficientes dados en un estado de entrada.</span><span class="sxs-lookup"><span data-stu-id="baaa8-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="baaa8-109">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="baaa8-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="baaa8-110">Los coeficientes que se van a codificar en un estado de entrada.</span><span class="sxs-lookup"><span data-stu-id="baaa8-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="baaa8-111">Salida: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="baaa8-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="baaa8-112">Operación de preparación de estado que prepara los coeficientes determinados como un estado de entrada en un registro determinado.</span><span class="sxs-lookup"><span data-stu-id="baaa8-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>