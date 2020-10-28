---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731980"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="79dfd-102">ObliviousAmplitudeAmplificationFromStatePreparation función)</span><span class="sxs-lookup"><span data-stu-id="79dfd-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="79dfd-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="79dfd-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="79dfd-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="79dfd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="79dfd-105">Amplificación de amplitud desconocen de Oracle para reflexiones parciales.</span><span class="sxs-lookup"><span data-stu-id="79dfd-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="79dfd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="79dfd-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="79dfd-107">fases: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="79dfd-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="79dfd-108">Fases de las reflexiones parciales</span><span class="sxs-lookup"><span data-stu-id="79dfd-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="79dfd-109">startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="79dfd-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="79dfd-110">Unitario Oracle $A $ que prepara el estado de inicio auxiliar</span><span class="sxs-lookup"><span data-stu-id="79dfd-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="79dfd-111">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="79dfd-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="79dfd-112">Unitario Oracle $O $ de tipo `ObliviousOracle` que actúa conjuntamente en el registro auxiliar y del sistema</span><span class="sxs-lookup"><span data-stu-id="79dfd-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="79dfd-113">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="79dfd-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="79dfd-114">Índice para el registro de la marca de un solo qubit</span><span class="sxs-lookup"><span data-stu-id="79dfd-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="79dfd-115">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unidad](xref:microsoft.quantum.lang-ref.unit) AJ + CTL</span><span class="sxs-lookup"><span data-stu-id="79dfd-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="79dfd-116">Operación que implementa la amplificación de amplitud de desconocen basada en reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="79dfd-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="79dfd-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="79dfd-117">Remarks</span></span>

<span data-ttu-id="79dfd-118">Esto impone condiciones más estrictas en la forma de los Estados de inicio y destino auxiliares que en `AmpAmpObliviousByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="79dfd-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="79dfd-119">Se supone que $A \ket {0} \_ f\ket {0} \_ A = \ket{\text{Start}} \_ {FA} $ prepara el estado de inicio auxiliar $ \ket{\text{Start}} \_ {FA} $ desde la base de cálculo $ \ket {0} \_ f\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="79dfd-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="79dfd-120">Se supone que el estado de destino está marcado por $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="79dfd-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="79dfd-121">Se supone que \begin{align} O\ket {\ Text {Start}} \_ {FA} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ Text {All}} \_ a\ket {\ Text {Target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} para algunos $U unitarios $.</span><span class="sxs-lookup"><span data-stu-id="79dfd-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>