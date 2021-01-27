---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 081541d93bf853fa0de1573038dc00c296432281
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855839"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="4574f-102">StatePreparationPositiveCoefficients función)</span><span class="sxs-lookup"><span data-stu-id="4574f-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="4574f-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="4574f-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="4574f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4574f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="4574f-105">StatePreparationPositiveCoefficients está en desuso.</span><span class="sxs-lookup"><span data-stu-id="4574f-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="4574f-106">Use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4574f-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="4574f-107">Devuelve una operación que prepara el estado de cuanto dado.</span><span class="sxs-lookup"><span data-stu-id="4574f-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="4574f-108">La operación devuelta $U $ prepara un estado de Quantum arbitrario $ \ket{\psi} $ con coeficientes positivos $ \ alpha_j \ge $0 desde el estado de base de cálculo $n $-qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="4574f-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="4574f-109">La acción de U en un registro recién asignado viene determinada por $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="4574f-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="4574f-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="4574f-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="4574f-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="4574f-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="4574f-112">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4574f-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4574f-113">Matriz de hasta $2 ^ n $ coeficientes $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="4574f-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="4574f-114">El coeficiente de $j $ TH indexa el número $ \ket{j} $ codificado en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="4574f-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="4574f-115">Salida: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="4574f-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4574f-116">Una operación de unitario de preparación de estado $U $.</span><span class="sxs-lookup"><span data-stu-id="4574f-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="4574f-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4574f-117">Example</span></span>

<span data-ttu-id="4574f-118">El siguiente fragmento de código prepara el estado de Quantum $ \ket{\psi} = \ sqrt {1/8} \ les {0} + \ sqrt {7/8} \ les {2} $ en el registro de qubit `qubitsLE` .</span><span class="sxs-lookup"><span data-stu-id="4574f-118">The following snippet prepares the quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let op = StatePreparationPositiveCoefficients(amplitudes);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="4574f-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4574f-119">Remarks</span></span>

<span data-ttu-id="4574f-120">Los coeficientes de entrada negativos $ \ alpha_j < $0 se tratarán como positivos con el valor $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="4574f-120">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="4574f-121">`coefficients` se rellenará con los elementos $ \ alpha_j = $0,0 si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="4574f-121">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>