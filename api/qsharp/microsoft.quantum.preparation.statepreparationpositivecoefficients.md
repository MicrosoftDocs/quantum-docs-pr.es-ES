---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732588"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="da1a2-102">StatePreparationPositiveCoefficients función)</span><span class="sxs-lookup"><span data-stu-id="da1a2-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="da1a2-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="da1a2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="da1a2-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da1a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da1a2-105">Devuelve una operación que prepara el estado de cuanto dado.</span><span class="sxs-lookup"><span data-stu-id="da1a2-105">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="da1a2-106">La operación devuelta $U $ prepara un estado de Quantum arbitrario $ \ket{\psi} $ con coeficientes positivos $ \ alpha_j \ge $0 desde el estado de base de cálculo $n $-qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="da1a2-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="da1a2-107">La acción de U en un registro recién asignado viene determinada por $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="da1a2-107">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="da1a2-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="da1a2-108">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="da1a2-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="da1a2-109">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="da1a2-110">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="da1a2-110">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="da1a2-111">Matriz de hasta $2 ^ n $ coeficientes $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="da1a2-111">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="da1a2-112">El coeficiente de $j $ TH indexa el número $ \ket{j} $ codificado en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="da1a2-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="da1a2-113">Salida: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) ajustable + CTL</span><span class="sxs-lookup"><span data-stu-id="da1a2-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="da1a2-114">Una operación de unitario de preparación de estado $U $.</span><span class="sxs-lookup"><span data-stu-id="da1a2-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="da1a2-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="da1a2-115">Remarks</span></span>

<span data-ttu-id="da1a2-116">Los coeficientes de entrada negativos $ \ alpha_j < $0 se tratarán como positivos con el valor $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="da1a2-116">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="da1a2-117">`coefficients` se rellenará con los elementos $ \ alpha_j = $0,0 si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="da1a2-117">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>