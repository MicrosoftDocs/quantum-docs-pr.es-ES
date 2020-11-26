---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: e910edb9bf432e6acb5c349ee6b9d65797aaaba7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211668"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="0ef16-102">NQubitsRequired función)</span><span class="sxs-lookup"><span data-stu-id="0ef16-102">NQubitsRequired function</span></span>

<span data-ttu-id="0ef16-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0ef16-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0ef16-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0ef16-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="0ef16-105">Devuelve el número de qubits necesario para aplicar un clasificador secuencial determinado.</span><span class="sxs-lookup"><span data-stu-id="0ef16-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="0ef16-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0ef16-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="0ef16-107">Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="0ef16-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="0ef16-108">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0ef16-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0ef16-109">Tamaño mínimo de un registro en el que se puede aplicar el clasificador secuencial.</span><span class="sxs-lookup"><span data-stu-id="0ef16-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>