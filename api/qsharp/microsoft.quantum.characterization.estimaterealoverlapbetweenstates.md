---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: Operación EstimateRealOverlapBetweenStates
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 1448e760294e958b152f4ceb3faf979441ca986d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851851"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a><span data-ttu-id="78df6-102">Operación EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="78df6-102">EstimateRealOverlapBetweenStates operation</span></span>

<span data-ttu-id="78df6-103">Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="78df6-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="78df6-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78df6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78df6-105">Dadas dos operaciones que preparan copias de un estado, calcula la parte real de la superposición entre los Estados preparados por cada operación.</span><span class="sxs-lookup"><span data-stu-id="78df6-105">Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="78df6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="78df6-106">Input</span></span>

### <a name="commonpreparation--qubit--unit--is-adj"></a><span data-ttu-id="78df6-107">commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="78df6-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="78df6-108">Operación que prepara un estado de entrada fijo.</span><span class="sxs-lookup"><span data-stu-id="78df6-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit--is-adj--ctl"></a><span data-ttu-id="78df6-109">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="78df6-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="78df6-110">Primera de las dos operaciones de preparación de estado que se van a comparar.</span><span class="sxs-lookup"><span data-stu-id="78df6-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj--ctl"></a><span data-ttu-id="78df6-111">preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="78df6-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="78df6-112">Segundo de las dos operaciones de preparación de estado que se van a comparar.</span><span class="sxs-lookup"><span data-stu-id="78df6-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="78df6-113">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="78df6-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="78df6-114">El número de qubits en el `commonPreparation` que `preparation1` `preparation2` todos los actos, y.</span><span class="sxs-lookup"><span data-stu-id="78df6-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="78df6-115">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="78df6-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="78df6-116">Número de medidas que se van a usar para calcular la superposición.</span><span class="sxs-lookup"><span data-stu-id="78df6-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="78df6-117">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78df6-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="78df6-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="78df6-118">Remarks</span></span>

<span data-ttu-id="78df6-119">Esta operación usa la prueba Hadamard para encontrar la parte real de $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $, donde $ \ket{\psi} $ es el estado preparado por `commonPreparation` , $U $ es la representación unitario de la acción de `preparation1` y donde $V $ corresponde a `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="78df6-119">This operation uses the Hadamard test to find the real part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="78df6-120">Referencias</span><span class="sxs-lookup"><span data-stu-id="78df6-120">References</span></span>

- <span data-ttu-id="78df6-121">Aharonov *et al.* [Quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="78df6-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="78df6-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="78df6-122">See Also</span></span>

- [<span data-ttu-id="78df6-123">Microsoft. Quantum. Caracterización. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="78df6-123">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [<span data-ttu-id="78df6-124">Microsoft. Quantum. Caracterización. EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="78df6-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)