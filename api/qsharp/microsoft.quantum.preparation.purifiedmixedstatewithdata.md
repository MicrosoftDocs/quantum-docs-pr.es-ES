---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: fc7bf8e6157af079ae4233ef45e67ce8ddfb8fe3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854278"
---
# <a name="purifiedmixedstatewithdata-function"></a><span data-ttu-id="a937e-102">PurifiedMixedStateWithData función)</span><span class="sxs-lookup"><span data-stu-id="a937e-102">PurifiedMixedStateWithData function</span></span>

<span data-ttu-id="a937e-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a937e-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a937e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a937e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a937e-105">Devuelve una operación que prepara una depuración de un estado mixto determinado, con un registro que representa una colección de datos determinada.</span><span class="sxs-lookup"><span data-stu-id="a937e-105">Returns an operation that prepares a a purification of a given mixed state, entangled with a register representing a given collection of data.</span></span>
<span data-ttu-id="a937e-106">Un "estado mixto depurado con datos" hace referencia a un estado de la forma σi √ Pi | i ⟩ | XI ⟩ | garbagei ⟩, donde cada XI es una bitstring Codificando datos adicionales asociados con el registro | i ⟩.</span><span class="sxs-lookup"><span data-stu-id="a937e-106">A "purified mixed state with data" refers to a state of the form Σᵢ √𝑝ᵢ |𝑖⟩ |𝑥ᵢ⟩ |garbageᵢ⟩, where each 𝑥ᵢ is a bitstring encoding additional data associated with the register |𝑖⟩.</span></span>

<span data-ttu-id="a937e-107">Vea https://arxiv.org/pdf/1805.03662.pdf?page=15 para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a937e-107">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="a937e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a937e-108">Description</span></span>

<span data-ttu-id="a937e-109">Usa la técnica de ROM Quantum para representar una matriz de densidad determinada, devolviendo esa representación como una operación de preparación del estado.</span><span class="sxs-lookup"><span data-stu-id="a937e-109">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="a937e-110">En concreto, dada una lista de $N $ coeficientes $ \ alpha_j $ y un bitstring $ \vec{x}_j $ asociado a cada coeficiente, esta función devuelve una operación que usa la técnica de ROM Quantum para preparar una aproximación $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _J} \bra{\vec{x}_j} \end{align} $ $ del estado mixto $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $, donde cada $p _j $ es una aproximación al coeficiente proporcionado $ \ alpha_j $, como $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ para cada $j $.</span><span class="sxs-lookup"><span data-stu-id="a937e-110">In particular, given a list of $N$ coefficients $\alpha_j$, and a bitstring $\vec{x}_j$ associated with each coefficient, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="a937e-111">Cuando se pasa un registro de índice y un registro de qubits de elementos no utilizados, inicialmente en el estado $ \ket {0} \ket{00\cdots 0}, la operación devuelta prepara ambos registros en la purificación de $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _J} \ket{\text{garbage} _J}, \end{align} $ $, de modo que al restablecer y desasignar el registro de elementos no utilizados, se establece la preparación deseada en el error $ \epsilon $ de destino.</span><span class="sxs-lookup"><span data-stu-id="a937e-111">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}_j} \ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="a937e-112">Entrada</span><span class="sxs-lookup"><span data-stu-id="a937e-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="a937e-113">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a937e-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a937e-114">El error de destino $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="a937e-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--doublebool"></a><span data-ttu-id="a937e-115">coeficientes: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []</span><span class="sxs-lookup"><span data-stu-id="a937e-115">coefficients : ([Double](xref:microsoft.quantum.lang-ref.double),[Bool](xref:microsoft.quantum.lang-ref.bool)[])[]</span></span>

<span data-ttu-id="a937e-116">Matriz de $N $ coeficientes que especifican la probabilidad de Estados de base, junto con el bitstring $ \vec{x} _j $ asociado a cada coeficiente.</span><span class="sxs-lookup"><span data-stu-id="a937e-116">Array of $N$ coefficients specifying the probability of basis states, along with the bitstring $\vec{x}_j$ associated with each coefficient.</span></span>
<span data-ttu-id="a937e-117">Los números negativos $-\ alpha_j $ se tratarán como positivos $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="a937e-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="a937e-118">Salida: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="a937e-118">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="a937e-119">Operación que prepara $ \tilde \rho $ como una depuración en un índice conjunto y un registro de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a937e-119">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="a937e-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a937e-120">Remarks</span></span>

<span data-ttu-id="a937e-121">Los coeficientes que se proporcionan a esta operación se normalizan después de la norma de 1, de modo que los coeficientes se consideran siempre para describir una distribución de probabilidad de categoría válida.</span><span class="sxs-lookup"><span data-stu-id="a937e-121">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="a937e-122">Referencias</span><span class="sxs-lookup"><span data-stu-id="a937e-122">References</span></span>

- <span data-ttu-id="a937e-123">Codifique los espectros electrónicos en los circuitos Quantum con la complejidad T lineal Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pálido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="a937e-123">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="a937e-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a937e-124">See Also</span></span>

- [<span data-ttu-id="a937e-125">Microsoft. Quantum. preparación. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="a937e-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)