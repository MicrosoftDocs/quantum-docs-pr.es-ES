---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: ed70d9f24af06f8918083307c98a5f6c4671f1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852936"
---
# <a name="inputencoder-function"></a><span data-ttu-id="bafba-102">InputEncoder función)</span><span class="sxs-lookup"><span data-stu-id="bafba-102">InputEncoder function</span></span>

<span data-ttu-id="bafba-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bafba-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="bafba-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bafba-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="bafba-105">Dado un conjunto de coeficientes y una tolerancia, devuelve una operación de preparación del estado que prepara cada coeficiente como la amplitud correspondiente del estado de la base de cálculo.</span><span class="sxs-lookup"><span data-stu-id="bafba-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="bafba-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bafba-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="bafba-107">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bafba-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bafba-108">Los coeficientes que se van a codificar en un estado de entrada.</span><span class="sxs-lookup"><span data-stu-id="bafba-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="bafba-109">Salida: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="bafba-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="bafba-110">Operación de preparación de estado que prepara los coeficientes determinados como un estado de entrada en un registro determinado.</span><span class="sxs-lookup"><span data-stu-id="bafba-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>