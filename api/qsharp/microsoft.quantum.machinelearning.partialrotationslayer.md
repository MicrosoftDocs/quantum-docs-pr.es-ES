---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ab964d2c43a13a5daf64aefdeccd1c26cd371ff4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732324"
---
# <a name="partialrotationslayer-function"></a><span data-ttu-id="1c998-102">PartialRotationsLayer función)</span><span class="sxs-lookup"><span data-stu-id="1c998-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="1c998-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1c998-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1c998-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c998-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c998-105">Devuelve una matriz de giros de un solo qubit a lo largo de un eje determinado, parametrizado por parámetros de modelo distintos.</span><span class="sxs-lookup"><span data-stu-id="1c998-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="1c998-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1c998-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="1c998-107">idxsQubits: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1c998-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1c998-108">Índices de qubits que se van a usar como destinos para cada rotación.</span><span class="sxs-lookup"><span data-stu-id="1c998-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="1c998-109">eje: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="1c998-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="1c998-110">Eje de giro de cada giro de la capa especificada.</span><span class="sxs-lookup"><span data-stu-id="1c998-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="1c998-111">Salida: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="1c998-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="1c998-112">Matriz de giros controlados sobre el eje dado, uno en cada `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="1c998-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>