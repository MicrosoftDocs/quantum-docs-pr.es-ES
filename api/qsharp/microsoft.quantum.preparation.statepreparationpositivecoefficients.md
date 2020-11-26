---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients función)
ms.date: 11/25/2020 12:00:00 AM
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
ms.openlocfilehash: 8f1fd7d77531996faf566adb78f452929d6cbd50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193257"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="40c57-102">StatePreparationPositiveCoefficients función)</span><span class="sxs-lookup"><span data-stu-id="40c57-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="40c57-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="40c57-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="40c57-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40c57-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="40c57-105">StatePreparationPositiveCoefficients está en desuso.</span><span class="sxs-lookup"><span data-stu-id="40c57-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="40c57-106">Use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="40c57-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="40c57-107">Devuelve una operación que prepara el estado de cuanto dado.</span><span class="sxs-lookup"><span data-stu-id="40c57-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="40c57-108">La operación devuelta $U $ prepara un estado de Quantum arbitrario $ \ket{\psi} $ con coeficientes positivos $ \ alpha_j \ge $0 desde el estado de base de cálculo $n $-qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="40c57-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="40c57-109">La acción de U en un registro recién asignado viene determinada por $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="40c57-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="40c57-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="40c57-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="40c57-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="40c57-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="40c57-112">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="40c57-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="40c57-113">Matriz de hasta $2 ^ n $ coeficientes $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="40c57-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="40c57-114">El coeficiente de $j $ TH indexa el número $ \ket{j} $ codificado en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="40c57-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="40c57-115">Salida: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="40c57-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="40c57-116">Una operación de unitario de preparación de estado $U $.</span><span class="sxs-lookup"><span data-stu-id="40c57-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="40c57-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="40c57-117">Remarks</span></span>

<span data-ttu-id="40c57-118">Los coeficientes de entrada negativos $ \ alpha_j < $0 se tratarán como positivos con el valor $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="40c57-118">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="40c57-119">`coefficients` se rellenará con los elementos $ \ alpha_j = $0,0 si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="40c57-119">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>