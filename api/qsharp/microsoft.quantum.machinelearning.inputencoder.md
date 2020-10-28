---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725949"
---
# <a name="inputencoder-function"></a><span data-ttu-id="45975-102">InputEncoder función)</span><span class="sxs-lookup"><span data-stu-id="45975-102">InputEncoder function</span></span>

<span data-ttu-id="45975-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="45975-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="45975-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45975-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45975-105">Dado un conjunto de coeficientes y una tolerancia, devuelve una operación de preparación del estado que prepara cada coeficiente como la amplitud correspondiente del estado de la base de cálculo.</span><span class="sxs-lookup"><span data-stu-id="45975-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="45975-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="45975-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="45975-107">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="45975-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="45975-108">Los coeficientes que se van a codificar en un estado de entrada.</span><span class="sxs-lookup"><span data-stu-id="45975-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="45975-109">Salida: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="45975-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="45975-110">Operación de preparación de estado que prepara los coeficientes determinados como un estado de entrada en un registro determinado.</span><span class="sxs-lookup"><span data-stu-id="45975-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>