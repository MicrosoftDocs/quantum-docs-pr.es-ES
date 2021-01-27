---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: Operación AdiabaticStateEnergyUnitary
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: d154f9f1f674dc7cf7af9807922b0897540087b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857955"
---
# <a name="adiabaticstateenergyunitary-operation"></a><span data-ttu-id="7f2cb-102">Operación AdiabaticStateEnergyUnitary</span><span class="sxs-lookup"><span data-stu-id="7f2cb-102">AdiabaticStateEnergyUnitary operation</span></span>

<span data-ttu-id="7f2cb-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7f2cb-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7f2cb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7f2cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7f2cb-105">Realiza la preparación del estado aplicando un `statePrepUnitary` en el estado de entrada, seguido de la preparación del estado de Adiabatic mediante `adiabaticUnitary` y, por último, la estimación de la fase con respecto a `qpeUnitary` en el estado resultante mediante `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="7f2cb-105">Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="7f2cb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7f2cb-106">Input</span></span>

### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="7f2cb-107">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="7f2cb-107">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7f2cb-108">Que representa una preparación del estado para el generador dinámico inicial.</span><span class="sxs-lookup"><span data-stu-id="7f2cb-108">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="7f2cb-109">adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="7f2cb-109">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7f2cb-110">Oracle que representa el algoritmo de evolución de Adiabatic que se va a usar para implementar los barridos en el estado final del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="7f2cb-110">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="7f2cb-111">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="7f2cb-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7f2cb-112">Un objeto de Oracle que representa un operador unitario $U $ que representa la evolución para el tiempo $ \delta t $ en un generador dinámico con el estado de la base $ \ket{\phi} $ y la energía del estado de la alimentación $E = \phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="7f2cb-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="7f2cb-113">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7f2cb-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="7f2cb-114">Operación que realiza una estimación de la fase en una operación de unitario determinada.</span><span class="sxs-lookup"><span data-stu-id="7f2cb-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="7f2cb-115">Consulte [estimación de fase iterativa](/quantum/libraries/characterization#iterative-phase-estimation) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="7f2cb-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="7f2cb-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7f2cb-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7f2cb-117">Registro de qubits que se va a usar para realizar la simulación.</span><span class="sxs-lookup"><span data-stu-id="7f2cb-117">A register of qubits to be used to perform the simulation.</span></span>



## <a name="output--double"></a><span data-ttu-id="7f2cb-118">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7f2cb-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7f2cb-119">Una estimación de $ \hat{\phi} $ de la energía de estado de la base $ \phi $ del generador representado por $U $.</span><span class="sxs-lookup"><span data-stu-id="7f2cb-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>