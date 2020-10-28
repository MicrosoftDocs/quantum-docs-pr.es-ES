---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: Operación EstimateOverlapBetweenStates
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 58a367c7ff7d13ac5c1eb1588fb8dac66414776c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728198"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="48bbf-102">Operación EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="48bbf-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="48bbf-103">Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="48bbf-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="48bbf-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48bbf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48bbf-105">Dadas dos operaciones que preparan copias de un estado, calcula la superposición cuadrada entre los Estados preparados por cada operación.</span><span class="sxs-lookup"><span data-stu-id="48bbf-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="48bbf-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="48bbf-106">Input</span></span>

### <a name="preparation1--qubit--unit-adj"></a><span data-ttu-id="48bbf-107">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48bbf-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="48bbf-108">Primera de las dos operaciones de preparación de estado que se van a comparar.</span><span class="sxs-lookup"><span data-stu-id="48bbf-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj"></a><span data-ttu-id="48bbf-109">preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48bbf-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="48bbf-110">Segundo de las dos operaciones de preparación de estado que se van a comparar.</span><span class="sxs-lookup"><span data-stu-id="48bbf-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="48bbf-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48bbf-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48bbf-112">El número de qubits en el `commonPreparation` que `preparation1` `preparation2` todos los actos, y.</span><span class="sxs-lookup"><span data-stu-id="48bbf-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="48bbf-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48bbf-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48bbf-114">Número de medidas que se van a usar para calcular la superposición.</span><span class="sxs-lookup"><span data-stu-id="48bbf-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="48bbf-115">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="48bbf-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="48bbf-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="48bbf-116">Remarks</span></span>

<span data-ttu-id="48bbf-117">Esta operación usa la prueba de intercambio para encontrar $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $, donde $U $ es la representación unitario de la acción de `preparation1` y donde $V $ corresponde a `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="48bbf-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="48bbf-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48bbf-118">See Also</span></span>

- [<span data-ttu-id="48bbf-119">Microsoft. Quantum. Caracterización. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="48bbf-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="48bbf-120">Microsoft. Quantum. Caracterización. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="48bbf-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)