---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operación EstimateTermExpectation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835669"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="2c5da-102">Operación EstimateTermExpectation</span><span class="sxs-lookup"><span data-stu-id="2c5da-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="2c5da-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="2c5da-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="2c5da-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2c5da-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="2c5da-105">Calcula la energía asociada a un determinado término de Jordan-Wigner Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="2c5da-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="2c5da-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c5da-106">Description</span></span>

<span data-ttu-id="2c5da-107">Esta operación calcula el valor de expectativa asociado a cada operador de medida y lo multiplica por el coeficiente correspondiente, mediante el muestreo.</span><span class="sxs-lookup"><span data-stu-id="2c5da-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="2c5da-108">Los resultados se agregan a una variable que contiene la energía del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="2c5da-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="2c5da-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="2c5da-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="2c5da-110">inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="2c5da-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="2c5da-111">La unitario usada para la preparación del estado.</span><span class="sxs-lookup"><span data-stu-id="2c5da-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="2c5da-112">OPS: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="2c5da-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="2c5da-113">Los operadores de medida del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="2c5da-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="2c5da-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2c5da-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2c5da-115">Coeficientes del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="2c5da-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="2c5da-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2c5da-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2c5da-117">El número de qubits necesario para simular el sistema molecular.</span><span class="sxs-lookup"><span data-stu-id="2c5da-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="2c5da-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2c5da-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2c5da-119">Número de muestras que se van a usar para la estimación de la expectativa de términos.</span><span class="sxs-lookup"><span data-stu-id="2c5da-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="2c5da-120">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2c5da-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2c5da-121">La energía asociada al término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="2c5da-121">The energy associated to the Jordan-Wigner term.</span></span>