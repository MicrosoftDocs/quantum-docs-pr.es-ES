---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: 8fa6db7d5616f8c561191e3da00a69b05041b279
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191693"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="4e41c-102">AmplitudeAmplificationFromPartialReflections función)</span><span class="sxs-lookup"><span data-stu-id="4e41c-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="4e41c-103">Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="4e41c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="4e41c-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e41c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e41c-105">Amplificación de amplitud por reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="4e41c-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="4e41c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4e41c-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="4e41c-107">fases: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="4e41c-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="4e41c-108">Fases de las reflexiones parciales</span><span class="sxs-lookup"><span data-stu-id="4e41c-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="4e41c-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="4e41c-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="4e41c-110">Operador de reflexión sobre el estado de inicio</span><span class="sxs-lookup"><span data-stu-id="4e41c-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="4e41c-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="4e41c-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="4e41c-112">Operador de reflexión sobre el estado de destino</span><span class="sxs-lookup"><span data-stu-id="4e41c-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="4e41c-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="4e41c-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4e41c-114">Operación que implementa la amplificación de amplitud por reflejos parciales.</span><span class="sxs-lookup"><span data-stu-id="4e41c-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e41c-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4e41c-115">Remarks</span></span>

<span data-ttu-id="4e41c-116">La amplificación de amplitud es un caso especial de amplificación de amplitud de desconocen en la que no hay qubits del sistema y desconocen Oracle está establecido en Identity.</span><span class="sxs-lookup"><span data-stu-id="4e41c-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="4e41c-117">En la mayoría de `startQubits` los casos, se inicializa en el estado $ \ket{\text{start}} \_ $1, que es el eigenstate $-$1 de `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="4e41c-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>