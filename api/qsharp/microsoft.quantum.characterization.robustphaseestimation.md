---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: Operación RobustPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 4b37c8275a5b2aee8534bacc5831281aa498b57d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851796"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="a89b6-102">Operación RobustPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="a89b6-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="a89b6-103">Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="a89b6-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="a89b6-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a89b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a89b6-105">Realiza el robusto algoritmo de estimación de fase de Quantum no iterativo para un determinado Oracle `U` y eigenstate, y proporciona una única estimación de valor real de la fase con ajuste de la varianza en el límite de Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="a89b6-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="a89b6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a89b6-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="a89b6-107">bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a89b6-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a89b6-108">Esto proporciona una estimación de $ \phi $ con la desviación estándar $ \sigma \le 2 \ pi/2 ^ \text{bitsPrecision} $ mediante un número de consultas que escalan como $ \sigma \le 10,7 \pi/\text{# de consultas} $.</span><span class="sxs-lookup"><span data-stu-id="a89b6-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="a89b6-109">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="a89b6-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="a89b6-110">Una operación que implementa $U ^ m $ para los enteros especificados $m $.</span><span class="sxs-lookup"><span data-stu-id="a89b6-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="a89b6-111">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a89b6-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a89b6-112">Un registro de Quantum en el que $U $ actúa.</span><span class="sxs-lookup"><span data-stu-id="a89b6-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="a89b6-113">Si almacena un eigenstate $ \ket{\phi} $ de $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ para $ \phi\in (-\pi, \pi] $ una fase desconocida.</span><span class="sxs-lookup"><span data-stu-id="a89b6-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="a89b6-114">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a89b6-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="a89b6-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a89b6-115">Remarks</span></span>

<span data-ttu-id="a89b6-116">En el límite de un gran número de consultas, Cramer-Rao límites inferiores para la desviación estándar de la estimación de $ \phi $ satisfaga $ \sigma \ge 2 \pi/\text{n.º de consultas} $.</span><span class="sxs-lookup"><span data-stu-id="a89b6-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="a89b6-117">Referencias</span><span class="sxs-lookup"><span data-stu-id="a89b6-117">References</span></span>

- <span data-ttu-id="a89b6-118">Calibración sólida de un Single-Qubit universal Gate-Set a través de una sólida estimación de fase de Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="a89b6-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>