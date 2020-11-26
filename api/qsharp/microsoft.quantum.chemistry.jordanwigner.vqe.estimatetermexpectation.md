---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operación EstimateTermExpectation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 3f0ff5037b1424abb6fb318bd49ffd89f545822d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224656"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="07a63-102">Operación EstimateTermExpectation</span><span class="sxs-lookup"><span data-stu-id="07a63-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="07a63-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="07a63-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="07a63-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="07a63-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="07a63-105">Calcula la energía asociada a un determinado término de Jordan-Wigner Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="07a63-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="07a63-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="07a63-106">Description</span></span>

<span data-ttu-id="07a63-107">Esta operación calcula el valor de expectativa asociado a cada operador de medida y lo multiplica por el coeficiente correspondiente, mediante el muestreo.</span><span class="sxs-lookup"><span data-stu-id="07a63-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="07a63-108">Los resultados se agregan a una variable que contiene la energía del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="07a63-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="07a63-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="07a63-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="07a63-110">inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="07a63-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="07a63-111">La unitario usada para la preparación del estado.</span><span class="sxs-lookup"><span data-stu-id="07a63-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="07a63-112">OPS: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="07a63-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="07a63-113">Los operadores de medida del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="07a63-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="07a63-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="07a63-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="07a63-115">Coeficientes del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="07a63-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="07a63-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="07a63-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="07a63-117">El número de qubits necesario para simular el sistema molecular.</span><span class="sxs-lookup"><span data-stu-id="07a63-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="07a63-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="07a63-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="07a63-119">Número de muestras que se van a usar para la estimación de la expectativa de términos.</span><span class="sxs-lookup"><span data-stu-id="07a63-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="07a63-120">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="07a63-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="07a63-121">La energía asociada al término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="07a63-121">The energy associated to the Jordan-Wigner term.</span></span>