---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854298"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="a000b-102">PurifiedMixedState función)</span><span class="sxs-lookup"><span data-stu-id="a000b-102">PurifiedMixedState function</span></span>

<span data-ttu-id="a000b-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a000b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a000b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a000b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a000b-105">Devuelve una operación que prepara una depuración de un estado mixto determinado.</span><span class="sxs-lookup"><span data-stu-id="a000b-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="a000b-106">Un "estado mixto depurado" se refiere a los Estados de la forma | ψ ⟩ = σi √ Pi | i ⟩ | garbagei ⟩ especificada por un vector de coeficientes {PI}.</span><span class="sxs-lookup"><span data-stu-id="a000b-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="a000b-107">Los Estados de este formulario se pueden reducir a los Estados mixtos p ≔ Pi | i ⟩ ⟨ i | mediante el seguimiento del registro de "elementos no utilizados" (es decir, un estado mixto que es diagonal en la base de cálculo).</span><span class="sxs-lookup"><span data-stu-id="a000b-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="a000b-108">Vea https://arxiv.org/pdf/1805.03662.pdf?page=15 para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a000b-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="a000b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a000b-109">Description</span></span>

<span data-ttu-id="a000b-110">Usa la técnica de ROM Quantum para representar una matriz de densidad determinada, devolviendo esa representación como una operación de preparación del estado.</span><span class="sxs-lookup"><span data-stu-id="a000b-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="a000b-111">En concreto, dada una lista de $N $ coeficientes $ \ alpha_j $, esta función devuelve una operación que usa la técnica de ROM Quantum para preparar una aproximación $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ del estado mixto $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $, donde cada $p _j $ es una aproximación al coeficiente proporcionado $ \ alpha_j $, que es $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ para cada $j $.</span><span class="sxs-lookup"><span data-stu-id="a000b-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="a000b-112">Cuando se pasa un registro de índice y un registro de qubits de elementos no utilizados, inicialmente, en el estado $ \ket {0} \ket{00\cdots 0}, la operación devuelta prepara ambos registros en la purificación de $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}, \end{align} $ $ de modo que el restablecimiento y la desasignación del registro de elementos no utilizados contengan la preparación deseada en el error $ \epsilon</span><span class="sxs-lookup"><span data-stu-id="a000b-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="a000b-113">Entrada</span><span class="sxs-lookup"><span data-stu-id="a000b-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="a000b-114">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a000b-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a000b-115">El error de destino $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="a000b-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="a000b-116">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a000b-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a000b-117">Matriz de $N $ coeficientes que especifican la probabilidad de Estados de base.</span><span class="sxs-lookup"><span data-stu-id="a000b-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="a000b-118">Los números negativos $-\ alpha_j $ se tratarán como positivos $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="a000b-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="a000b-119">Salida: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="a000b-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="a000b-120">Operación que prepara $ \tilde \rho $ como una depuración en un índice conjunto y un registro de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a000b-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="example"></a><span data-ttu-id="a000b-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a000b-121">Example</span></span>

<span data-ttu-id="a000b-122">El siguiente fragmento de código prepara una purificación del estado $3 $-qubit $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, donde $ \vec\alpha = (1.0, 2,0, 3,0, 4,0, 5,0) $ y el error de destino es $10 ^ {-3} $:</span><span class="sxs-lookup"><span data-stu-id="a000b-122">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0, 2.0, 3.0, 4.0, 5.0)$, and the target error is $10^{-3}$:</span></span>

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="a000b-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a000b-123">Remarks</span></span>

<span data-ttu-id="a000b-124">Los coeficientes que se proporcionan a esta operación se normalizan después de la norma de 1, de modo que los coeficientes se consideran siempre para describir una distribución de probabilidad de categoría válida.</span><span class="sxs-lookup"><span data-stu-id="a000b-124">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="a000b-125">Referencias</span><span class="sxs-lookup"><span data-stu-id="a000b-125">References</span></span>

- <span data-ttu-id="a000b-126">Codifique los espectros electrónicos en los circuitos Quantum con la complejidad T lineal Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pálido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="a000b-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="a000b-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a000b-127">See Also</span></span>

- [<span data-ttu-id="a000b-128">Microsoft. Quantum. preparación. PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="a000b-128">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)