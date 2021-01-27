---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: 8f6c1bf3dfef3152a6ba8eada0980d6940724259
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854962"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="abd55-102">NQubitsRequired función)</span><span class="sxs-lookup"><span data-stu-id="abd55-102">NQubitsRequired function</span></span>

<span data-ttu-id="abd55-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="abd55-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="abd55-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="abd55-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="abd55-105">Devuelve el número de qubits necesario para aplicar un clasificador secuencial determinado.</span><span class="sxs-lookup"><span data-stu-id="abd55-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="abd55-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="abd55-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="abd55-107">Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="abd55-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="abd55-108">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="abd55-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="abd55-109">Tamaño mínimo de un registro en el que se puede aplicar el clasificador secuencial.</span><span class="sxs-lookup"><span data-stu-id="abd55-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>