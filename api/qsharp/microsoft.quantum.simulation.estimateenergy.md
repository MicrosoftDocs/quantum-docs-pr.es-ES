---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: Operación EstimateEnergy
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: f9243557718e12d168afadbf641492291afd1704
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856761"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="05396-102">Operación EstimateEnergy</span><span class="sxs-lookup"><span data-stu-id="05396-102">EstimateEnergy operation</span></span>

<span data-ttu-id="05396-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="05396-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="05396-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="05396-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="05396-105">Realiza la preparación del estado aplicando un `statePrepUnitary` en una estimación de fase de estado de entrada asignada automáticamente con respecto a `qpeUnitary` en el estado resultante mediante `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="05396-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="05396-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="05396-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="05396-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="05396-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="05396-108">Número de qubits utilizadas para realizar la simulación.</span><span class="sxs-lookup"><span data-stu-id="05396-108">Number of qubits used to perform simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="05396-109">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="05396-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="05396-110">Que representa una preparación del estado para el generador dinámico inicial.</span><span class="sxs-lookup"><span data-stu-id="05396-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="05396-111">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="05396-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="05396-112">Un objeto de Oracle que representa un operador unitario $U $ que representa la evolución para el tiempo $ \delta t $ en un generador dinámico con el estado de la base $ \ket{\phi} $ y la energía del estado de la alimentación $E = \phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="05396-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="05396-113">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="05396-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="05396-114">Operación que realiza una estimación de la fase en una operación de unitario determinada.</span><span class="sxs-lookup"><span data-stu-id="05396-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="05396-115">Consulte [estimación de fase iterativa](/quantum/libraries/characterization#iterative-phase-estimation) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="05396-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="05396-116">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="05396-116">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="05396-117">Una estimación de $ \hat{\phi} $ de la energía de estado de la alimentación $ \phi $ de la energía de estado de la alimentación del generador representada por $U $.</span><span class="sxs-lookup"><span data-stu-id="05396-117">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the ground state energy of the generator represented by $U$.</span></span>