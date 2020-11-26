---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Operación PrepareUniformSuperposition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 9b9f182ed7c1ea24ae74b8a2321a309042a17c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230096"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="55361-102">Operación PrepareUniformSuperposition</span><span class="sxs-lookup"><span data-stu-id="55361-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="55361-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="55361-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="55361-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55361-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55361-105">Crea una superposición uniforme sobre los Estados que codifican 0 a `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="55361-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="55361-106">Es decir, esta $U unitario $ crea una superposición uniforme sobre todos los Estados $0 $ en $M-$1, dado un estado de entrada $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="55361-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="55361-107">En otras palabras, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="55361-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="55361-108">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="55361-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="55361-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="55361-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="55361-110">nIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55361-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55361-111">El número deseado de Estados $M $ en la superposición uniforme.</span><span class="sxs-lookup"><span data-stu-id="55361-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="55361-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="55361-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="55361-113">El registro qubit que almacena los Estados de número en `LittleEndian` formato.</span><span class="sxs-lookup"><span data-stu-id="55361-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="55361-114">Este registro debe ser capaz de almacenar el número $M-$1 y se supone que se ha inicializado en el estado $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="55361-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="55361-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55361-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="55361-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="55361-116">Remarks</span></span>

<span data-ttu-id="55361-117">La operación es adjointable, pero requiere que `indexRegister` esté en una superposición uniforme `nIndices` en los Estados de la primera base en ese caso.</span><span class="sxs-lookup"><span data-stu-id="55361-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>