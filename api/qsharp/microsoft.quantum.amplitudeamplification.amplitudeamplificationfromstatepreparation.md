---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 7725ff327e327578ff36242a2b1bc6d03fab0d0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732044"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="e824c-102">AmplitudeAmplificationFromStatePreparation función)</span><span class="sxs-lookup"><span data-stu-id="e824c-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="e824c-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e824c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e824c-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e824c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e824c-105">Amplificación de amplitud de Oracle para reflexiones parciales.</span><span class="sxs-lookup"><span data-stu-id="e824c-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e824c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e824c-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="e824c-107">fases: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="e824c-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="e824c-108">Fases de las reflexiones parciales</span><span class="sxs-lookup"><span data-stu-id="e824c-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="e824c-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="e824c-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="e824c-110">Unitario de Oracle $A $ que prepara el estado de inicio</span><span class="sxs-lookup"><span data-stu-id="e824c-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="e824c-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e824c-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e824c-112">Índice para marcar qubit</span><span class="sxs-lookup"><span data-stu-id="e824c-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="e824c-113">Salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="e824c-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e824c-114">Operación que implementa la amplificación de amplitud por parte de Oracle implementada por reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="e824c-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="e824c-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e824c-115">Remarks</span></span>

<span data-ttu-id="e824c-116">Esto impone condiciones más estrictas en la forma de los Estados de inicio y de destino que en `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="e824c-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="e824c-117">Se supone que el estado de destino está marcado por $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="e824c-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="e824c-118">Se supone que \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \Ket {0} \_ f\cdots, \end{align} en la mayoría de los casos, `flagQubit` y `auxiliaryRegister` se inicializan en el estado $ \ket {0} \_ {f} \ket {0} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="e824c-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>