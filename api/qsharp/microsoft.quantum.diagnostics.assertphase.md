---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operación AssertPhase
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202267"
---
# <a name="assertphase-operation"></a><span data-ttu-id="c677a-102">Operación AssertPhase</span><span class="sxs-lookup"><span data-stu-id="c677a-102">AssertPhase operation</span></span>

<span data-ttu-id="c677a-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c677a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c677a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c677a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c677a-105">Declara que la fase de un estado de superposición igual tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="c677a-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="c677a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c677a-106">Description</span></span>

<span data-ttu-id="c677a-107">Esta operación garantiza que la fase $ \phi $ de un estado de Quantum que se puede expresar como $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ les {0} + e ^ {-i\phi} \ les {1} ) $ para algunos $t reales arbitrarios $ tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="c677a-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="c677a-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="c677a-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="c677a-109">se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c677a-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c677a-110">El valor esperado de $ \phi \en (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="c677a-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="c677a-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c677a-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c677a-112">Qubit que almacena el estado esperado.</span><span class="sxs-lookup"><span data-stu-id="c677a-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="c677a-113">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c677a-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c677a-114">Tolerancia absoluta en la diferencia entre real y expected.</span><span class="sxs-lookup"><span data-stu-id="c677a-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c677a-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c677a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

