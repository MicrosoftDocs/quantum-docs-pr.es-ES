---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: Operación RandomWalkPhaseEstimation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 5e0c0871b916ff51b85dec8703111788b5204bc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726434"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="7abe3-102">Operación RandomWalkPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="7abe3-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="7abe3-103">Espacio de nombres: [Microsoft. Quantum. Research. Caracterización](xref:Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="7abe3-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="7abe3-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7abe3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7abe3-105">Realiza una estimación de la fase iterativa mediante un recorrido aleatorio para la inferencia bayesiana aproximada en los resultados de medidas clásicas de una determinada Oracle y eigenstate.</span><span class="sxs-lookup"><span data-stu-id="7abe3-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="7abe3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7abe3-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="7abe3-107">initialMean: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7abe3-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7abe3-108">Media de la distribución previa normal inicial a través de $ \phi $.</span><span class="sxs-lookup"><span data-stu-id="7abe3-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="7abe3-109">initialStdDev: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7abe3-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7abe3-110">Desviación estándar de la distribución previa normal inicial a través de $ \phi $.</span><span class="sxs-lookup"><span data-stu-id="7abe3-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="7abe3-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7abe3-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7abe3-112">Número de medidas que se van a aceptar en la estimación posterior final.</span><span class="sxs-lookup"><span data-stu-id="7abe3-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="7abe3-113">maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7abe3-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7abe3-114">Número total de medidas que se pueden realizar antes de que se considere que se ha producido un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="7abe3-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="7abe3-115">desenredar: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7abe3-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7abe3-116">Número de resultados que se deben olvidar cuando se produce un error en las comprobaciones de coherencia.</span><span class="sxs-lookup"><span data-stu-id="7abe3-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="7abe3-117">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="7abe3-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="7abe3-118">Operación que representa una $U unitario $ de modo que $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $ with Unknown Phase $ \phi \en \mathbb{R} ^ + $.</span><span class="sxs-lookup"><span data-stu-id="7abe3-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="7abe3-119">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7abe3-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7abe3-120">Registro en el que $U $ actúa.</span><span class="sxs-lookup"><span data-stu-id="7abe3-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="7abe3-121">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7abe3-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7abe3-122">La estimación final $ \hat{\phi} \mathrel{: =} \expect [\phi] $, donde la expectativa se encuentra sobre el asiento en función de todos los datos aceptados.</span><span class="sxs-lookup"><span data-stu-id="7abe3-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="7abe3-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7abe3-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="7abe3-124">Estimación de fase iterativa y Eigenstates</span><span class="sxs-lookup"><span data-stu-id="7abe3-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="7abe3-125">En general, el registro de entrada `eigenstate` no necesita ser un eigenstate $ \ket{\phi} $ de $U $, pero puede ser una superposición sobre eigenstates.</span><span class="sxs-lookup"><span data-stu-id="7abe3-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="7abe3-126">Supongamos que el estado de entrada lo proporciona \begin{align} \ket{\psi} & = \sum \_ {j} \alpha \_ j \ket{\phi \_ j}, \end{align} donde $ \{ \alpha \_ j \} $ son coeficientes complejos, de modo que $ \sum \_ j | \alpha \_ j | ^ 2 = $1 y Where $U \ket{\phi \_ j} = \phi \_ j\ket {\ Phi \_ j} $.</span><span class="sxs-lookup"><span data-stu-id="7abe3-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="7abe3-127">Después, realizar una estimación de la fase iterativa se convergirá en un único eigenstate, como se describe en la [Guía de desarrollo](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span><span class="sxs-lookup"><span data-stu-id="7abe3-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="7abe3-128">Diseño de experimentos</span><span class="sxs-lookup"><span data-stu-id="7abe3-128">Experiment Design</span></span>

<span data-ttu-id="7abe3-129">Los tiempos de medición $t $ y los ángulos de inversion $ \theta $ pasados a `oracle` se eligen según la heurística de la *partícula* , \Begin{align} \theta \sim \Pr (\phi), \quad t \approx \frac {1} {\variance{\phi}}.</span><span class="sxs-lookup"><span data-stu-id="7abe3-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic* , \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="7abe3-130">\end{align} esta heurística es óptima para reducir la desviación posterior esperada en la estimación de la fase iterativa bajo la suposición de una normal anterior.</span><span class="sxs-lookup"><span data-stu-id="7abe3-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="7abe3-131">Idoneidad</span><span class="sxs-lookup"><span data-stu-id="7abe3-131">Optimality</span></span>

<span data-ttu-id="7abe3-132">Esta operación aproxima el estimador óptimo para la fase $ \phi $, tal como se ha evaluado mediante la pérdida cuadrática $L (\phi, \hat{\phi}) \mathrel{: =} (\phi-\hat{\phi}) ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="7abe3-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="7abe3-133">Consulte [estimación de la fase bayesiana](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) para obtener más detalles sobre las estadísticas de la estimación de la fase iterativa.</span><span class="sxs-lookup"><span data-stu-id="7abe3-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="7abe3-134">Referencias</span><span class="sxs-lookup"><span data-stu-id="7abe3-134">References</span></span>

- <span data-ttu-id="7abe3-135">Ferrie *et al.* 2011 [doi: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv: 1110.3067](https://arxiv.org/abs/1110.3067).</span><span class="sxs-lookup"><span data-stu-id="7abe3-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="7abe3-136">Wiebe *et al.* 2013 [doi: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv: 1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="7abe3-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="7abe3-137">Wiebe y Granade 2018 *(en preparación)* .</span><span class="sxs-lookup"><span data-stu-id="7abe3-137">Wiebe and Granade 2018 *(in preparation)* .</span></span>