---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operación AssertPhase
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830079"
---
# <a name="assertphase-operation"></a><span data-ttu-id="9bdde-102">Operación AssertPhase</span><span class="sxs-lookup"><span data-stu-id="9bdde-102">AssertPhase operation</span></span>

<span data-ttu-id="9bdde-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9bdde-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9bdde-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9bdde-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9bdde-105">Declara que la fase de un estado de superposición igual tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="9bdde-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="9bdde-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bdde-106">Description</span></span>

<span data-ttu-id="9bdde-107">Esta operación garantiza que la fase $ \phi $ de un estado de Quantum que se puede expresar como $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ les {0} + e ^ {-i\phi} \ les {1} ) $ para algunos $t reales arbitrarios $ tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="9bdde-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="9bdde-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="9bdde-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="9bdde-109">se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9bdde-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9bdde-110">El valor esperado de $ \phi \en (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="9bdde-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="9bdde-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9bdde-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9bdde-112">Qubit que almacena el estado esperado.</span><span class="sxs-lookup"><span data-stu-id="9bdde-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="9bdde-113">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9bdde-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9bdde-114">Tolerancia absoluta en la diferencia entre real y expected.</span><span class="sxs-lookup"><span data-stu-id="9bdde-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9bdde-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9bdde-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="9bdde-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9bdde-116">Example</span></span>

<span data-ttu-id="9bdde-117">La siguiente aserción se realiza correctamente: `qubit` está en el estado $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ les {0} + e ^ {i 0.5} \ sqrt {1/2} \ les {1} $;</span><span class="sxs-lookup"><span data-stu-id="9bdde-117">The following assert succeeds: `qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.0,qubit,10e-10);`

<span data-ttu-id="9bdde-118">`qubit` está en el estado $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ les {0} + e ^ {-i 0.5} \ sqrt {1/2} \ les {1} $;</span><span class="sxs-lookup"><span data-stu-id="9bdde-118">`qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{-i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.5,qubit,10e-10);`

<span data-ttu-id="9bdde-119">`qubit` está en el estado $ \ket{\psi} = e ^ {-i 2.2} \ sqrt {1/2} \ les {0} + e ^ {i 0,2} \ sqrt {1/2} \ les {1} $;</span><span class="sxs-lookup"><span data-stu-id="9bdde-119">`qubit` is in state $\ket{\psi}=e^{-i 2.2}\sqrt{1/2}\ket{0}+e^{i 0.2}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(-1.2,qubit,10e-10);`