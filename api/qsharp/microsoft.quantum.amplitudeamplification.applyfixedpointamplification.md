---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Operación ApplyFixedPointAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847228"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="33645-102">Operación ApplyFixedPointAmplification</span><span class="sxs-lookup"><span data-stu-id="33645-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="33645-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="33645-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="33645-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="33645-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="33645-105">Algoritmo de amplificación de amplitud Fixed-Point</span><span class="sxs-lookup"><span data-stu-id="33645-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="33645-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="33645-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="33645-107">statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="33645-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="33645-108">Oracle unitario que prepara el estado de inicio.</span><span class="sxs-lookup"><span data-stu-id="33645-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="33645-109">startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="33645-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="33645-110">Registro de qubit</span><span class="sxs-lookup"><span data-stu-id="33645-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="33645-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33645-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="33645-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="33645-112">Remarks</span></span>

<span data-ttu-id="33645-113">El valor de startQubits debe estar en el estado $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="33645-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="33645-114">Esta operación recorre en iteración varias consultas en potencias de $2 $ hasta que se alcanza un número máximo de consultas o se encuentra el estado de destino.</span><span class="sxs-lookup"><span data-stu-id="33645-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>