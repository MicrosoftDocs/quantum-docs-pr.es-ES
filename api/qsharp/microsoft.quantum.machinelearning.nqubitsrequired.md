---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: d7ed687e9c75ed7cc71917aa1cdf32a6fbb93106
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732973"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="1fab7-102">NQubitsRequired función)</span><span class="sxs-lookup"><span data-stu-id="1fab7-102">NQubitsRequired function</span></span>

<span data-ttu-id="1fab7-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1fab7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1fab7-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1fab7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1fab7-105">Devuelve el número de qubits necesario para aplicar un clasificador secuencial determinado.</span><span class="sxs-lookup"><span data-stu-id="1fab7-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="1fab7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1fab7-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="1fab7-107">Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="1fab7-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="1fab7-108">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1fab7-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1fab7-109">Tamaño mínimo de un registro en el que se puede aplicar el clasificador secuencial.</span><span class="sxs-lookup"><span data-stu-id="1fab7-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>