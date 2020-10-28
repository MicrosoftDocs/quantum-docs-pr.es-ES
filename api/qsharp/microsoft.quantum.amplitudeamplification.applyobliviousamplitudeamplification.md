---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: Operación ApplyObliviousAmplitudeAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: a1bda344b1097c7ab3240bc6d9cd0d8df80b9662
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732005"
---
# <a name="applyobliviousamplitudeamplification-operation"></a><span data-ttu-id="c3ba1-102">Operación ApplyObliviousAmplitudeAmplification</span><span class="sxs-lookup"><span data-stu-id="c3ba1-102">ApplyObliviousAmplitudeAmplification operation</span></span>

<span data-ttu-id="c3ba1-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="c3ba1-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="c3ba1-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3ba1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3ba1-105">Amplificación de amplitud de desconocen mediante la especificación de reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-105">Oblivious amplitude amplification by specifying partial reflections.</span></span>

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c3ba1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c3ba1-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="c3ba1-107">fases: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="c3ba1-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="c3ba1-108">Fases de las reflexiones parciales</span><span class="sxs-lookup"><span data-stu-id="c3ba1-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="c3ba1-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="c3ba1-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="c3ba1-110">Operador de reflexión sobre el estado de inicio del registro auxiliar</span><span class="sxs-lookup"><span data-stu-id="c3ba1-110">Reflection operator about start state of auxiliary register</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="c3ba1-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="c3ba1-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="c3ba1-112">Operador de reflexión sobre el estado de destino del registro auxiliar</span><span class="sxs-lookup"><span data-stu-id="c3ba1-112">Reflection operator about target state of auxiliary register</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="c3ba1-113">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="c3ba1-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="c3ba1-114">Unitario Oracle $O $ de tipo `ObliviousOracle` que actúa conjuntamente en los registros auxiliares y del sistema.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-114">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system registers.</span></span>


### <a name="auxiliaryregister--qubit"></a><span data-ttu-id="c3ba1-115">auxiliaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c3ba1-115">auxiliaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c3ba1-116">Registro auxiliar</span><span class="sxs-lookup"><span data-stu-id="c3ba1-116">Auxiliary register</span></span>


### <a name="systemregister--qubit"></a><span data-ttu-id="c3ba1-117">systemRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c3ba1-117">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c3ba1-118">Registro del sistema</span><span class="sxs-lookup"><span data-stu-id="c3ba1-118">System register</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3ba1-119">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3ba1-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c3ba1-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c3ba1-120">Remarks</span></span>

<span data-ttu-id="c3ba1-121">Dado un estado de inicio auxiliar determinado $ \ket{\text{Start}} \_ a $, un estado de destino auxiliar determinado $ \ket{\text{Target}} \_ a $ y cualquier estado del sistema $ \ket{\psi} \_ s $, supongamos que \begin{align} O\ket {\ Text {Start}} \_ a\ket {\ PSI} \_ s = \lambda\ket{\text{Target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \Ket{\text{Target} ^ \perp} a\cdots \end{align} para una unidad \_ de $U $.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-121">Given a particular auxiliary start state $\ket{\text{start}}\_a$, a particular auxiliary target state $\ket{\text{target}}\_a$, and any system state $\ket{\psi}\_s$, suppose that \begin{align} O\ket{\text{start}}\_a\ket{\psi}\_s= \lambda\ket{\text{target}}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{\text{target}^\perp}\_a\cdots \end{align} for some unitary $U$.</span></span>
<span data-ttu-id="c3ba1-122">Mediante una secuencia de reflexiones sobre los Estados de inicio y de destino en el registro auxiliar intercalados por las aplicaciones de `signalOracle` y su contiguo, se puede modificar la probabilidad de éxito de aplicar U.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-122">By a sequence of reflections about the start and target states on the auxiliary register interleaved by applications of `signalOracle` and its adjoint, the success probability of applying U may be altered.</span></span>

<span data-ttu-id="c3ba1-123">En la mayoría de `auxiliaryRegister` los casos, se inicializa en el estado $ \ket{\text{Start}} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-123">In most cases, `auxiliaryRegister` is initialized in the state $\ket{\text{start}}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="c3ba1-124">Referencias</span><span class="sxs-lookup"><span data-stu-id="c3ba1-124">References</span></span>

<span data-ttu-id="c3ba1-125">Vea</span><span class="sxs-lookup"><span data-stu-id="c3ba1-125">See</span></span>

- <span data-ttu-id="c3ba1-126">[ *D.W. Berry, AM Childs, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) para la versión estándar.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma* ](https://arxiv.org/abs/1312.1414) for the standard version.</span></span>
  <span data-ttu-id="c3ba1-127">Vea</span><span class="sxs-lookup"><span data-stu-id="c3ba1-127">See</span></span>
- <span data-ttu-id="c3ba1-128">[ *G.H. Low, I.L. Chuang*](https://arxiv.org/abs/1610.06546) para una generalización de reflexiones parciales.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-128">[ *G.H. Low, I.L. Chuang* ](https://arxiv.org/abs/1610.06546) for a generalization to partial reflections.</span></span>