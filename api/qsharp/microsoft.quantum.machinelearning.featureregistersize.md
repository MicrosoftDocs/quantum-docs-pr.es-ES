---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196419"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="71e8f-102">FeatureRegisterSize función)</span><span class="sxs-lookup"><span data-stu-id="71e8f-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="71e8f-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="71e8f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="71e8f-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="71e8f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="71e8f-105">Devuelve el número de qubits necesarios para codificar un vector de característica determinado.</span><span class="sxs-lookup"><span data-stu-id="71e8f-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="71e8f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="71e8f-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="71e8f-107">ejemplo: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="71e8f-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="71e8f-108">Un vector de característica de ejemplo que se va a codificar en un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="71e8f-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="71e8f-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71e8f-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="71e8f-110">Tamaño necesario para codificar `sample` en un registro qubit, expresado como un número de qubits.</span><span class="sxs-lookup"><span data-stu-id="71e8f-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>