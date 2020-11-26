---
uid: Microsoft.Quantum.Simulation.EstimateEnergyWithAdiabaticEvolution
title: Operación EstimateEnergyWithAdiabaticEvolution
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergyWithAdiabaticEvolution
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: b279d35418b8f013ad0d72e9a980c9bf6ce0689a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225336"
---
# <a name="estimateenergywithadiabaticevolution-operation"></a><span data-ttu-id="a8dd5-102">Operación EstimateEnergyWithAdiabaticEvolution</span><span class="sxs-lookup"><span data-stu-id="a8dd5-102">EstimateEnergyWithAdiabaticEvolution operation</span></span>

<span data-ttu-id="a8dd5-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a8dd5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a8dd5-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8dd5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8dd5-105">Realiza la preparación del estado aplicando a un `statePrepUnitary` Estado de entrada asignado automáticamente, seguido de la preparación del estado de Adiabatic mediante `adiabaticUnitary` y, por último, la estimación de la fase con respecto a `qpeUnitary` en el estado resultante mediante `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="a8dd5-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergyWithAdiabaticEvolution (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="a8dd5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a8dd5-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="a8dd5-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a8dd5-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a8dd5-108">Número de qubits que se usan para la simulación.</span><span class="sxs-lookup"><span data-stu-id="a8dd5-108">Number of qubits used for the simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="a8dd5-109">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="a8dd5-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a8dd5-110">Que representa una preparación del estado para el generador dinámico inicial.</span><span class="sxs-lookup"><span data-stu-id="a8dd5-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="a8dd5-111">adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="a8dd5-111">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a8dd5-112">Oracle que representa el algoritmo de evolución de Adiabatic que se va a usar para implementar los barridos en el estado final del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="a8dd5-112">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="a8dd5-113">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="a8dd5-113">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a8dd5-114">Un objeto de Oracle que representa un operador unitario $U $ que representa la evolución para el tiempo $ \delta t $ en un generador dinámico con el estado de la base $ \ket{\phi} $ y la energía del estado de la alimentación $E = \phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="a8dd5-114">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="a8dd5-115">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a8dd5-115">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="a8dd5-116">Operación que realiza una estimación de la fase en una operación de unitario determinada.</span><span class="sxs-lookup"><span data-stu-id="a8dd5-116">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="a8dd5-117">Consulte [estimación de fase iterativa](/quantum/libraries/characterization#iterative-phase-estimation) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="a8dd5-117">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="a8dd5-118">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a8dd5-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a8dd5-119">Una estimación de $ \hat{\phi} $ de la energía de estado de la base $ \phi $ del generador representado por $U $.</span><span class="sxs-lookup"><span data-stu-id="a8dd5-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>