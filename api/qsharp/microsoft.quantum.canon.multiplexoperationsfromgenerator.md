---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: Operación MultiplexOperationsFromGenerator
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 9fbbd9268d4a6b9f3d5fd203969f4bbeebe81b68
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205956"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="2c133-102">Operación MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="2c133-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="2c133-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2c133-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2c133-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c133-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c133-105">Aplica una operación de unitario con control de multiplicación $U $ que aplica una $V unitario _j $ cuando está controlada por el estado de n-qubit número $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="2c133-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="2c133-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="2c133-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2c133-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="2c133-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="2c133-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> ' t = la [unidad](xref:microsoft.quantum.lang-ref.unit)  de> es ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="2c133-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="2c133-109">Una tupla en la que el primer elemento `Int` es el número de unitaries $N $ y el segundo elemento `(Int -> ('T => () is Adj + Ctl))` es una función que toma un entero $j $ in $ [0, N-1] $ y genera la operación unitario $V _J $.</span><span class="sxs-lookup"><span data-stu-id="2c133-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="2c133-110">Índice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2c133-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2c133-111">$n registro de control $-qubit que codifica los Estados de número $ \ket{j} $ en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="2c133-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="2c133-112">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="2c133-112">target : 'T</span></span>

<span data-ttu-id="2c133-113">Registro qubit genérico en el que $V _j $ actúa.</span><span class="sxs-lookup"><span data-stu-id="2c133-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c133-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c133-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2c133-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2c133-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2c133-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="2c133-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="2c133-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2c133-117">Remarks</span></span>

<span data-ttu-id="2c133-118">`coefficients` se rellenará con elementos Identity si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="2c133-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="2c133-119">Esta implementación usa $n qubits-$1 auxiliar.</span><span class="sxs-lookup"><span data-stu-id="2c133-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="2c133-120">Referencias</span><span class="sxs-lookup"><span data-stu-id="2c133-120">References</span></span>

- [<span data-ttu-id="2c133-121">*Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su*, arXiv: 1711.10980</span><span class="sxs-lookup"><span data-stu-id="2c133-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su*, arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)