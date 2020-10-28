---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Operación ApplyFixedPointAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732021"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="c4b17-102">Operación ApplyFixedPointAmplification</span><span class="sxs-lookup"><span data-stu-id="c4b17-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="c4b17-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="c4b17-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="c4b17-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4b17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4b17-105">Algoritmo de amplificación de amplitud Fixed-Point</span><span class="sxs-lookup"><span data-stu-id="c4b17-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c4b17-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c4b17-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="c4b17-107">statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="c4b17-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="c4b17-108">Oracle unitario que prepara el estado de inicio.</span><span class="sxs-lookup"><span data-stu-id="c4b17-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="c4b17-109">startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c4b17-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c4b17-110">Registro de qubit</span><span class="sxs-lookup"><span data-stu-id="c4b17-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4b17-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4b17-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c4b17-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c4b17-112">Remarks</span></span>

<span data-ttu-id="c4b17-113">El valor de startQubits debe estar en el estado $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="c4b17-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="c4b17-114">Esta operación recorre en iteración varias consultas en potencias de $2 $ hasta que se alcanza un número máximo de consultas o se encuentra el estado de destino.</span><span class="sxs-lookup"><span data-stu-id="c4b17-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>