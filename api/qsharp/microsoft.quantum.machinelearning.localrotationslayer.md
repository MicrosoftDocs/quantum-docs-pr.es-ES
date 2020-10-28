---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 8a3557f76d5d7a7b6375e5640cf6d11172cd38a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732916"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="b5c79-102">LocalRotationsLayer función)</span><span class="sxs-lookup"><span data-stu-id="b5c79-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="b5c79-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b5c79-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b5c79-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b5c79-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b5c79-105">Devuelve una matriz de giros no controlados (qubit) a lo largo de un eje determinado, con un giro para cada qubit de un registro, parametrizado por parámetros de modelo distintos.</span><span class="sxs-lookup"><span data-stu-id="b5c79-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="b5c79-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b5c79-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="b5c79-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5c79-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5c79-108">El número de qubits en función de la capa especificada.</span><span class="sxs-lookup"><span data-stu-id="b5c79-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="b5c79-109">eje: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="b5c79-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="b5c79-110">Eje de giro de cada giro de la capa especificada.</span><span class="sxs-lookup"><span data-stu-id="b5c79-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="b5c79-111">Salida: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="b5c79-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="b5c79-112">Matriz de giros controlados sobre el eje dado, uno en cada `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="b5c79-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>