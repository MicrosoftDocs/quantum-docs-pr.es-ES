---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731109"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="f8c0e-102">CyclicEntanglingLayer función)</span><span class="sxs-lookup"><span data-stu-id="f8c0e-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="f8c0e-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f8c0e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f8c0e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f8c0e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f8c0e-105">Devuelve una matriz de rotaciones de control individual a lo largo de un eje determinado, organizadas cíclicamente por un registro de qubits y parametrizado por parámetros de modelo distintos.</span><span class="sxs-lookup"><span data-stu-id="f8c0e-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="f8c0e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f8c0e-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="f8c0e-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f8c0e-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f8c0e-108">El número de qubits en función de la capa especificada.</span><span class="sxs-lookup"><span data-stu-id="f8c0e-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="f8c0e-109">eje: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="f8c0e-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="f8c0e-110">Eje de giro de cada giro de la capa especificada.</span><span class="sxs-lookup"><span data-stu-id="f8c0e-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="f8c0e-111">STRIDE: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f8c0e-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f8c0e-112">La separación entre el destino y los índices de control para cada rotación.</span><span class="sxs-lookup"><span data-stu-id="f8c0e-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="f8c0e-113">Salida: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="f8c0e-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="f8c0e-114">Una matriz de rotaciones controladas de dos qubits que se distribuyen cíclicamente a lo largo de un registro de `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="f8c0e-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>