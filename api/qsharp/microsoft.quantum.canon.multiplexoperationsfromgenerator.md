---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: Operación MultiplexOperationsFromGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2fde0bf391568f39128e6dca4b535aa6b78407c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728541"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="bd4ae-102">Operación MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="bd4ae-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="bd4ae-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd4ae-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd4ae-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bd4ae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bd4ae-105">Aplica una operación de unitario con control de multiplicación $U $ que aplica una $V unitario _j $ cuando está controlada por el estado de n-qubit número $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="bd4ae-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="bd4ae-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="bd4ae-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="bd4ae-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="bd4ae-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a><span data-ttu-id="bd4ae-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) ajustable + CTL)</span><span class="sxs-lookup"><span data-stu-id="bd4ae-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="bd4ae-109">Una tupla en la que el primer elemento `Int` es el número de unitaries $N $ y el segundo elemento `(Int -> ('T => () is Adj + Ctl))` es una función que toma un entero $j $ in $ [0, N-1] $ y genera la operación unitario $V _J $.</span><span class="sxs-lookup"><span data-stu-id="bd4ae-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="bd4ae-110">Índice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bd4ae-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bd4ae-111">$n registro de control $-qubit que codifica los Estados de número $ \ket{j} $ en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="bd4ae-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="bd4ae-112">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="bd4ae-112">target : 'T</span></span>

<span data-ttu-id="bd4ae-113">Registro qubit genérico en el que $V _j $ actúa.</span><span class="sxs-lookup"><span data-stu-id="bd4ae-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd4ae-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd4ae-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bd4ae-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="bd4ae-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd4ae-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="bd4ae-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="bd4ae-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bd4ae-117">Remarks</span></span>

<span data-ttu-id="bd4ae-118">`coefficients` se rellenará con elementos Identity si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="bd4ae-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="bd4ae-119">Esta implementación usa $n qubits-$1 auxiliar.</span><span class="sxs-lookup"><span data-stu-id="bd4ae-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="bd4ae-120">Referencias</span><span class="sxs-lookup"><span data-stu-id="bd4ae-120">References</span></span>

- [<span data-ttu-id="bd4ae-121">*Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su* , arXiv: 1711.10980</span><span class="sxs-lookup"><span data-stu-id="bd4ae-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su* , arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)