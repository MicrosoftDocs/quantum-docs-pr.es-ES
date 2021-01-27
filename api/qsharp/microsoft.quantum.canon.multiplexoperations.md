---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Operación MultiplexOperations
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 1cf483bb0d3b7cc43d271b65a2363fab95ff0f3b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852526"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="d1a7d-102">Operación MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="d1a7d-102">MultiplexOperations operation</span></span>

<span data-ttu-id="d1a7d-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d1a7d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d1a7d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1a7d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1a7d-105">Aplica una matriz de operaciones controlada por una matriz de Estados numéricos.</span><span class="sxs-lookup"><span data-stu-id="d1a7d-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="d1a7d-106">Es decir, se aplica la operación unitario controlada por multiplicación $U $ que aplica una $V unitario _j $ cuando se controla mediante $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="d1a7d-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="d1a7d-107">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="d1a7d-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d1a7d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="d1a7d-108">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="d1a7d-109">unitaries: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="d1a7d-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="d1a7d-110">Matriz de hasta una operación de hasta $2 ^ n $ unitarios.</span><span class="sxs-lookup"><span data-stu-id="d1a7d-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="d1a7d-111">La operación $j $ TH está indizada por el número $ \ket{j} $ codificado en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="d1a7d-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="d1a7d-112">Índice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d1a7d-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d1a7d-113">$n registro de control $-qubit que codifica los Estados de número $ \ket{j} $ en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="d1a7d-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="d1a7d-114">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="d1a7d-114">target : 'T</span></span>

<span data-ttu-id="d1a7d-115">Registro qubit genérico en el que $V _j $ actúa.</span><span class="sxs-lookup"><span data-stu-id="d1a7d-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d1a7d-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1a7d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d1a7d-117">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d1a7d-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d1a7d-118">Traslada</span><span class="sxs-lookup"><span data-stu-id="d1a7d-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="d1a7d-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d1a7d-119">Remarks</span></span>

<span data-ttu-id="d1a7d-120">`coefficients` se rellenará con elementos Identity si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="d1a7d-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="d1a7d-121">Esta implementación usa $n qubits-$1 auxiliar.</span><span class="sxs-lookup"><span data-stu-id="d1a7d-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="d1a7d-122">Referencias</span><span class="sxs-lookup"><span data-stu-id="d1a7d-122">References</span></span>

- <span data-ttu-id="d1a7d-123">Hacia la primera simulación de Quantum con la velocidad de Quantum Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="d1a7d-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>