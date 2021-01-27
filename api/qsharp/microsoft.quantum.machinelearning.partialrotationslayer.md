---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: e230df9b28c59e1d532d5b36adf90efa01f0f33e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852915"
---
# <a name="partialrotationslayer-function"></a><span data-ttu-id="10f9f-102">PartialRotationsLayer función)</span><span class="sxs-lookup"><span data-stu-id="10f9f-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="10f9f-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="10f9f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="10f9f-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="10f9f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="10f9f-105">Devuelve una matriz de giros de un solo qubit a lo largo de un eje determinado, parametrizado por parámetros de modelo distintos.</span><span class="sxs-lookup"><span data-stu-id="10f9f-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="10f9f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="10f9f-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="10f9f-107">idxsQubits: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="10f9f-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="10f9f-108">Índices de qubits que se van a usar como destinos para cada rotación.</span><span class="sxs-lookup"><span data-stu-id="10f9f-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="10f9f-109">eje: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="10f9f-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="10f9f-110">Eje de giro de cada giro de la capa especificada.</span><span class="sxs-lookup"><span data-stu-id="10f9f-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="10f9f-111">Salida: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="10f9f-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="10f9f-112">Matriz de giros controlados sobre el eje dado, uno en cada `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="10f9f-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>