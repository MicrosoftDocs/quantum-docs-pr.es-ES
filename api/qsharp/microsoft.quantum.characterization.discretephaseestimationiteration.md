---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: Operación DiscretePhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 167b53d7108c64d11a4f258d17e90ba78d7dd8d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728229"
---
# <a name="discretephaseestimationiteration-operation"></a><span data-ttu-id="5e727-102">Operación DiscretePhaseEstimationIteration</span><span class="sxs-lookup"><span data-stu-id="5e727-102">DiscretePhaseEstimationIteration operation</span></span>

<span data-ttu-id="5e727-103">Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="5e727-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="5e727-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e727-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e727-105">Realiza una sola iteración de un algoritmo de estimación de fase iterativo (controlado por clases) con potencias enteras de una clase unitario de Oracle.</span><span class="sxs-lookup"><span data-stu-id="5e727-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.</span></span>

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="5e727-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5e727-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="5e727-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="5e727-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="5e727-108">Operación que actúa en un entero y un registro, de modo que $U ^ m $ se aplica al registro dado, donde $U $ es la unidad de medida cuya fase se va a estimar y donde $m $ es la potencia del entero que se da a Oracle.</span><span class="sxs-lookup"><span data-stu-id="5e727-108">Operation acting on an integer and a register, such that $U^m$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $m$ is the integer power given to the oracle</span></span>


### <a name="power--int"></a><span data-ttu-id="5e727-109">potencia: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5e727-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5e727-110">Número de veces que se va a aplicar la unitario de Oracle.</span><span class="sxs-lookup"><span data-stu-id="5e727-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="5e727-111">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e727-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5e727-112">Ángulo por el que se va a invertir la fase en el control qubit antes de actuar en el estado de destino.</span><span class="sxs-lookup"><span data-stu-id="5e727-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="5e727-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5e727-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5e727-114">Registro del estado sobre el que ha actuado la unitario de Oracle.</span><span class="sxs-lookup"><span data-stu-id="5e727-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="5e727-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5e727-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5e727-116">Qubit auxiliar que se usa para controlar la aplicación de la determinada Oracle.</span><span class="sxs-lookup"><span data-stu-id="5e727-116">An auxiliary qubit used to control the application of the given oracle.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e727-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e727-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

