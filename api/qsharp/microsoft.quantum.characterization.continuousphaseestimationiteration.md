---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operación ContinuousPhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728234"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="63c2d-102">Operación ContinuousPhaseEstimationIteration</span><span class="sxs-lookup"><span data-stu-id="63c2d-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="63c2d-103">Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="63c2d-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="63c2d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63c2d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63c2d-105">Realiza una sola iteración de un algoritmo de estimación de fases iterativo (controlado por clases) que usa poderes reales arbitrarios de una unitario de Oracle.</span><span class="sxs-lookup"><span data-stu-id="63c2d-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="63c2d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="63c2d-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="63c2d-107">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="63c2d-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="63c2d-108">Operación que actúa en un doble $t $ y un registro, de modo que $U ^ t $ se aplica al registro dado, donde $U $ es la unitario cuya fase se va a estimar y donde $t $ es la potencia del entero que se ha dado a Oracle.</span><span class="sxs-lookup"><span data-stu-id="63c2d-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="63c2d-109">tiempo: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="63c2d-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="63c2d-110">Número de veces que se va a aplicar la unitario de Oracle.</span><span class="sxs-lookup"><span data-stu-id="63c2d-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="63c2d-111">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="63c2d-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="63c2d-112">Ángulo por el que se va a invertir la fase en el control qubit antes de actuar en el estado de destino.</span><span class="sxs-lookup"><span data-stu-id="63c2d-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="63c2d-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="63c2d-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="63c2d-114">Registro del estado sobre el que ha actuado la unitario de Oracle.</span><span class="sxs-lookup"><span data-stu-id="63c2d-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="63c2d-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="63c2d-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="63c2d-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63c2d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
