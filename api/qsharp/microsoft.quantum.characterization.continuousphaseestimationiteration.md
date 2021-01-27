---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operación ContinuousPhaseEstimationIteration
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851907"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="28e13-102">Operación ContinuousPhaseEstimationIteration</span><span class="sxs-lookup"><span data-stu-id="28e13-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="28e13-103">Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="28e13-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="28e13-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28e13-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28e13-105">Realiza una sola iteración de un algoritmo de estimación de fases iterativo (controlado por clases) que usa poderes reales arbitrarios de una unitario de Oracle.</span><span class="sxs-lookup"><span data-stu-id="28e13-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="28e13-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="28e13-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="28e13-107">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="28e13-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="28e13-108">Operación que actúa en un doble $t $ y un registro, de modo que $U ^ t $ se aplica al registro dado, donde $U $ es la unitario cuya fase se va a estimar y donde $t $ es la potencia del entero que se ha dado a Oracle.</span><span class="sxs-lookup"><span data-stu-id="28e13-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="28e13-109">tiempo: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="28e13-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="28e13-110">Número de veces que se va a aplicar la unitario de Oracle.</span><span class="sxs-lookup"><span data-stu-id="28e13-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="28e13-111">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="28e13-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="28e13-112">Ángulo por el que se va a invertir la fase en el control qubit antes de actuar en el estado de destino.</span><span class="sxs-lookup"><span data-stu-id="28e13-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="28e13-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="28e13-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="28e13-114">Registro del estado sobre el que ha actuado la unitario de Oracle.</span><span class="sxs-lookup"><span data-stu-id="28e13-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="28e13-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="28e13-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="28e13-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28e13-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

