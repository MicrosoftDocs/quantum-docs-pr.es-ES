---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732045"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="99688-102">AmplitudeAmplificationFromPartialReflections función)</span><span class="sxs-lookup"><span data-stu-id="99688-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="99688-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="99688-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="99688-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99688-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99688-105">Amplificación de amplitud por reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="99688-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="99688-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="99688-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="99688-107">fases: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="99688-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="99688-108">Fases de las reflexiones parciales</span><span class="sxs-lookup"><span data-stu-id="99688-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="99688-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="99688-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="99688-110">Operador de reflexión sobre el estado de inicio</span><span class="sxs-lookup"><span data-stu-id="99688-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="99688-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="99688-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="99688-112">Operador de reflexión sobre el estado de destino</span><span class="sxs-lookup"><span data-stu-id="99688-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="99688-113">Salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="99688-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="99688-114">Operación que implementa la amplificación de amplitud por reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="99688-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="99688-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="99688-115">Remarks</span></span>

<span data-ttu-id="99688-116">La amplificación de amplitud es un caso especial de amplificación de amplitud de desconocen en la que no hay qubits del sistema y desconocen Oracle está establecido en Identity.</span><span class="sxs-lookup"><span data-stu-id="99688-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="99688-117">En la mayoría de `startQubits` los casos, se inicializa en el estado $ \ket{\text{start}} \_ $1, que es el eigenstate $-$1 de `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="99688-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>