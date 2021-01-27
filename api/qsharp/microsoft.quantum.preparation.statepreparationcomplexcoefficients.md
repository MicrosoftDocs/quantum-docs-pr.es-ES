---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: c16df0fe075b15cff745a6b7d5b79aac39c14d09
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856134"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="16b54-102">StatePreparationComplexCoefficients función)</span><span class="sxs-lookup"><span data-stu-id="16b54-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="16b54-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="16b54-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="16b54-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16b54-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="16b54-105">StatePreparationComplexCoefficients está en desuso.</span><span class="sxs-lookup"><span data-stu-id="16b54-105">StatePreparationComplexCoefficients has been deprecated.</span></span> <span data-ttu-id="16b54-106">Use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="16b54-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="16b54-107">Devuelve una operación que prepara un estado de Quantum específico.</span><span class="sxs-lookup"><span data-stu-id="16b54-107">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="16b54-108">La operación devuelta $U $ prepara un estado de Quantum arbitrario $ \ket{\psi} $ con coeficientes complejos $r _j e ^ {i t_j} $ del estado de la base de cálculo $n $-qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="16b54-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="16b54-109">La acción de U en un registro recién asignado viene determinada por $ $ \begin{align} U\ket {0... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="16b54-109">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="16b54-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="16b54-110">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="16b54-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="16b54-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="16b54-112">coeficientes: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="16b54-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="16b54-113">Matriz de hasta $2 ^ n $ coeficientes complejos representados por su valor absoluto y la fase $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="16b54-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="16b54-114">El coeficiente de $j $ TH indexa el número $ \ket{j} $ codificado en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="16b54-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="16b54-115">Salida: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="16b54-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="16b54-116">Una operación de unitario de preparación de estado $U $.</span><span class="sxs-lookup"><span data-stu-id="16b54-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="16b54-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16b54-117">Example</span></span>

<span data-ttu-id="16b54-118">El siguiente fragmento de código prepara el estado de Quantum $ \ket{\psi} = e ^ {i 0.1} \ sqrt {1/8} \ les {0} + \ sqrt {7/8} \ les {2} $ en el registro de qubit `qubitsLE` .</span><span class="sxs-lookup"><span data-stu-id="16b54-118">The following snippet prepares the quantum state $\ket{\psi}=e^{i 0.1}\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let phases = [0.1, 0.0, 0.0, 0.0];
mutable complexNumbers = new ComplexPolar[4];
for (idx in 0..3) {
    set complexNumbers[idx] = ComplexPolar(amplitudes[idx], phases[idx]);
}
let op = StatePreparationComplexCoefficients(complexNumbers);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="16b54-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="16b54-119">Remarks</span></span>

<span data-ttu-id="16b54-120">Los coeficientes de entrada negativos $r _j < $0 se tratarán como positivos con el valor $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="16b54-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="16b54-121">`coefficients` se rellenará con los elementos $ (r_j, t_j) = (0,0, 0,0) $ si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="16b54-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>