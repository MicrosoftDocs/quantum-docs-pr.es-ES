---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: aa5f09f2e1fde878b523b4efc20b86c26ac738ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216547"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="2a13b-102">DecomposedIntoTimeStepsCA función)</span><span class="sxs-lookup"><span data-stu-id="2a13b-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="2a13b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2a13b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2a13b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a13b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a13b-105">Devuelve una operación que implementa el integrador Trotter – Suzuki para una operación determinada.</span><span class="sxs-lookup"><span data-stu-id="2a13b-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="2a13b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2a13b-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="2a13b-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a13b-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a13b-108">El número de operaciones que se van a descomponer en pasos temporales.</span><span class="sxs-lookup"><span data-stu-id="2a13b-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="2a13b-109">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="2a13b-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2a13b-110">Una operación que acepta una entrada de índice (tipo `Int` ) y una entrada de hora (tipo `Double` ) para la descomposición.</span><span class="sxs-lookup"><span data-stu-id="2a13b-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="2a13b-111">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a13b-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a13b-112">Selecciona el orden del integrador Trotter – Suzuki que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="2a13b-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="2a13b-113">Orden 1 e incluso pedidos 2, 4, 6,... Actualmente se admiten.</span><span class="sxs-lookup"><span data-stu-id="2a13b-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit--is-adj--ctl"></a><span data-ttu-id="2a13b-114">Salida: ([Double](xref:microsoft.quantum.lang-ref.double), ' t) => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="2a13b-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2a13b-115">Devuelve una unitario que implementa el integrador Trotter – Suzuki, donde el primer parámetro `Double` es el tamaño del paso de integración y el segundo parámetro es el destino sobre el que se actuó.</span><span class="sxs-lookup"><span data-stu-id="2a13b-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2a13b-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2a13b-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2a13b-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="2a13b-117">'T</span></span>

<span data-ttu-id="2a13b-118">Tipo en el que debe actuar cada paso de tiempo; Normalmente, `Qubit[]` o `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="2a13b-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a13b-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2a13b-119">Remarks</span></span>

<span data-ttu-id="2a13b-120">Cuando se llama con `order` igual a `1` , esta función devuelve una operación que se puede simular con el orden más bajo Trotter – Suzuki Integrator $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $, donde hemos seguido la notación de [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) y dejar que $ \lambda $ sea la hora de la evolución (representada por la primera entrada de la operación devuelta). y tienen que dejar que $ \{ H_j \} _ {j = 1} ^ {m} $ sea el conjunto de generadores dinámicos (sesgado-Hermitian) que se integran de forma que `op(j, lambda, _)` se simula mediante el operador unitario $e ^ {H_j \lambda} $.</span><span class="sxs-lookup"><span data-stu-id="2a13b-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="2a13b-121">De forma similar, un `order` de `2` devuelve el segundo orden simétrico Trotter – Suzuki Integrator $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.</span><span class="sxs-lookup"><span data-stu-id="2a13b-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="2a13b-122">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="2a13b-122">\end{align} $$</span></span>

<span data-ttu-id="2a13b-123">Los valores pares más altos de `order` se implementan mediante la construcción recursiva de [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="2a13b-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="2a13b-124">Referencias</span><span class="sxs-lookup"><span data-stu-id="2a13b-124">References</span></span>

- [<span data-ttu-id="2a13b-125">*D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders*</span><span class="sxs-lookup"><span data-stu-id="2a13b-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)