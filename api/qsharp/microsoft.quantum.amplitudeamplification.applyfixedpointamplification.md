---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Operación ApplyFixedPointAmplification
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: 13e70b1ebd5e3bf0996e6a76f4bffe57ca2d2250
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191540"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="ba3e0-102">Operación ApplyFixedPointAmplification</span><span class="sxs-lookup"><span data-stu-id="ba3e0-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="ba3e0-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="ba3e0-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="ba3e0-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba3e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba3e0-105">Algoritmo de amplificación de amplitud Fixed-Point</span><span class="sxs-lookup"><span data-stu-id="ba3e0-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ba3e0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ba3e0-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="ba3e0-107">statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="ba3e0-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="ba3e0-108">Oracle unitario que prepara el estado de inicio.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="ba3e0-109">startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ba3e0-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ba3e0-110">Registro de qubit</span><span class="sxs-lookup"><span data-stu-id="ba3e0-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="ba3e0-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ba3e0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ba3e0-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba3e0-112">Remarks</span></span>

<span data-ttu-id="ba3e0-113">El valor de startQubits debe estar en el estado $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="ba3e0-114">Esta operación recorre en iteración varias consultas en potencias de $2 $ hasta que se alcanza un número máximo de consultas o se encuentra el estado de destino.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>