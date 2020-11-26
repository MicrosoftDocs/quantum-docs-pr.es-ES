---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: Operación ApproximatelyPrepareArbitraryState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > ApproximatelyPrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 9e1b172258acd0cb09b824a773e7e79d44fec20c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193716"
---
# <a name="approximatelypreparearbitrarystate-operation"></a><span data-ttu-id="17fe2-102">Operación ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="17fe2-102">ApproximatelyPrepareArbitraryState operation</span></span>

<span data-ttu-id="17fe2-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="17fe2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="17fe2-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17fe2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="17fe2-105">ApproximatelyPrepareArbitraryState está en desuso.</span><span class="sxs-lookup"><span data-stu-id="17fe2-105">ApproximatelyPrepareArbitraryState has been deprecated.</span></span> <span data-ttu-id="17fe2-106">Use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="17fe2-106">Please use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="17fe2-107">Dado un conjunto de coeficientes y un registro de Quantum con codificación Little-endian, prepara un estado en ese registro descrito por los coeficientes determinados, hasta una tolerancia de aproximación determinada.</span><span class="sxs-lookup"><span data-stu-id="17fe2-107">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="17fe2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="17fe2-108">Description</span></span>

<span data-ttu-id="17fe2-109">Esta operación prepara un estado de Quantum arbitrario $ \ket{\psi} $ con coeficientes complejos $r _j e ^ {i t_j} $ del estado de la base de cálculo $n $-qubit $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="17fe2-109">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="17fe2-110">En concreto, la acción de esta operación la puede simular una transformación unitario $U $ que actúa en el estado de todos los ceros como</span><span class="sxs-lookup"><span data-stu-id="17fe2-110">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="17fe2-111">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="17fe2-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="17fe2-112">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="17fe2-112">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="17fe2-113">Entrada</span><span class="sxs-lookup"><span data-stu-id="17fe2-113">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="17fe2-114">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="17fe2-114">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="17fe2-115">Tolerancia de aproximación que se va a usar al preparar el estado dado.</span><span class="sxs-lookup"><span data-stu-id="17fe2-115">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="17fe2-116">coeficientes: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="17fe2-116">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="17fe2-117">Matriz de hasta $2 ^ n $ coeficientes complejos representados por su valor absoluto y la fase $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="17fe2-117">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="17fe2-118">El coeficiente de $j $ TH indexa el número $ \ket{j} $ codificado en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="17fe2-118">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="17fe2-119">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="17fe2-119">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="17fe2-120">Qubit registra los Estados de número de codificación en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="17fe2-120">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="17fe2-121">Se espera que se inicialice en el estado de base de cálculo $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="17fe2-121">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17fe2-122">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17fe2-122">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="17fe2-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="17fe2-123">Remarks</span></span>

<span data-ttu-id="17fe2-124">Los coeficientes de entrada negativos $r _j < $0 se tratarán como positivos con el valor $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="17fe2-124">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="17fe2-125">`coefficients` se rellenará con los elementos $ (r_j, t_j) = (0,0, 0,0) $ si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="17fe2-125">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="17fe2-126">Referencias</span><span class="sxs-lookup"><span data-stu-id="17fe2-126">References</span></span>

- <span data-ttu-id="17fe2-127">Síntesis de los circuitos de lógica de Quantum Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="17fe2-127">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="17fe2-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17fe2-128">See Also</span></span>

- [<span data-ttu-id="17fe2-129">Microsoft. Quantum. preparación. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="17fe2-129">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)