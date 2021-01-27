---
uid: Microsoft.Quantum.MachineLearning.ApplySequentialClassifier
title: Operación ApplySequentialClassifier
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApplySequentialClassifier
qsharp.summary: Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.
ms.openlocfilehash: 8186bc57e64a52e123bef8e3556d3385c4df7034
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851436"
---
# <a name="applysequentialclassifier-operation"></a><span data-ttu-id="d772e-102">Operación ApplySequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="d772e-102">ApplySequentialClassifier operation</span></span>

<span data-ttu-id="d772e-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d772e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d772e-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d772e-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d772e-105">Dada la estructura y la parametrización de un clasificador secuencial, aplica el clasificador a un registro de qubits.</span><span class="sxs-lookup"><span data-stu-id="d772e-105">Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.</span></span>

```qsharp
operation ApplySequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d772e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d772e-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="d772e-107">Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="d772e-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="d772e-108">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d772e-108">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d772e-109">Registro de destino al que se debe aplicar el clasificador.</span><span class="sxs-lookup"><span data-stu-id="d772e-109">A target register to which the classifier should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d772e-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d772e-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

