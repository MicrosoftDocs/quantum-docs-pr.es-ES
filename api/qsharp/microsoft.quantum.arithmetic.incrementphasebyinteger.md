---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Operación IncrementPhaseByInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 54b83b3d4460c05478543c51f8f9c0b0e7f5b1fa
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222922"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="80f0a-102">Operación IncrementPhaseByInteger</span><span class="sxs-lookup"><span data-stu-id="80f0a-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="80f0a-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="80f0a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="80f0a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80f0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80f0a-105">Incrementa un registro de Quantum sin signo mediante un entero clásico, usando giros de fase.</span><span class="sxs-lookup"><span data-stu-id="80f0a-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="80f0a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="80f0a-106">Description</span></span>

<span data-ttu-id="80f0a-107">Supongamos que `target` codifica un entero sin signo $x $ en una codificación Little-endian y que `increment` es igual a $a $.</span><span class="sxs-lookup"><span data-stu-id="80f0a-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="80f0a-108">A continuación, esta operación implementa la unitario $ \ket{x} \mapsto \ket{x + a} $, donde la adición se realiza en módulo $2 ^ n $, donde $n = \texttt{Length (Target!)} $.</span><span class="sxs-lookup"><span data-stu-id="80f0a-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="80f0a-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="80f0a-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="80f0a-110">incremento: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="80f0a-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="80f0a-111">Entero por el que `target` se incrementa.</span><span class="sxs-lookup"><span data-stu-id="80f0a-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="80f0a-112">destino: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="80f0a-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="80f0a-113">Un registro de Quantum codifica un entero sin signo mediante la codificación Little-endian en la base dual (QFT).</span><span class="sxs-lookup"><span data-stu-id="80f0a-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80f0a-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80f0a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="80f0a-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="80f0a-115">Remarks</span></span>

<span data-ttu-id="80f0a-116">Tenga en cuenta que se ha simplificado el circuito porque el incremento es una constante clásica, no un registro de Quantum.</span><span class="sxs-lookup"><span data-stu-id="80f0a-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="80f0a-117">Vea la ilustración de la [ Página 6 de arXiv: Quant-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) para el diagrama del circuito y la explicación.</span><span class="sxs-lookup"><span data-stu-id="80f0a-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="80f0a-118">Referencias</span><span class="sxs-lookup"><span data-stu-id="80f0a-118">References</span></span>

- [<span data-ttu-id="80f0a-119">*Thomas G. Draper*, arXiv: Quant-pH/0008033</span><span class="sxs-lookup"><span data-stu-id="80f0a-119"> *Thomas G. Draper*, arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="80f0a-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="80f0a-120">See Also</span></span>

- [<span data-ttu-id="80f0a-121">Microsoft. Quantum. aritmético. IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="80f0a-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)