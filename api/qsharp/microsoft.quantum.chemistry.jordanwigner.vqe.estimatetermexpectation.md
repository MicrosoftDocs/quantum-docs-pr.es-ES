---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operación EstimateTermExpectation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727653"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="7c53b-102">Operación EstimateTermExpectation</span><span class="sxs-lookup"><span data-stu-id="7c53b-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="7c53b-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="7c53b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="7c53b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c53b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c53b-105">Calcula la energía asociada a un determinado término de Jordan-Wigner Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="7c53b-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="7c53b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c53b-106">Description</span></span>

<span data-ttu-id="7c53b-107">Esta operación calcula el valor de expectativa asociado a cada operador de medida y lo multiplica por el coeficiente correspondiente, mediante el muestreo.</span><span class="sxs-lookup"><span data-stu-id="7c53b-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="7c53b-108">Los resultados se agregan a una variable que contiene la energía del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="7c53b-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="7c53b-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="7c53b-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit-adj"></a><span data-ttu-id="7c53b-110">inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c53b-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7c53b-111">La unitario usada para la preparación del estado.</span><span class="sxs-lookup"><span data-stu-id="7c53b-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="7c53b-112">OPS: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="7c53b-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="7c53b-113">Los operadores de medida del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="7c53b-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="7c53b-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7c53b-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7c53b-115">Coeficientes del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="7c53b-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="7c53b-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7c53b-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7c53b-117">El número de qubits necesario para simular el sistema molecular.</span><span class="sxs-lookup"><span data-stu-id="7c53b-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="7c53b-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7c53b-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7c53b-119">Número de muestras que se van a usar para la estimación de la expectativa de términos.</span><span class="sxs-lookup"><span data-stu-id="7c53b-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="7c53b-120">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7c53b-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7c53b-121">La energía asociada al término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="7c53b-121">The energy associated to the Jordan-Wigner term.</span></span>