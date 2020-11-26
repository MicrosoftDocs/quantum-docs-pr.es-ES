---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: Operación IncrementPhaseByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 6a39ce49dfa28c1f1cbe6b29e526144c3ac19e53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222888"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="9e35e-102">Operación IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="9e35e-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="9e35e-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9e35e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9e35e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9e35e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9e35e-105">Realiza un incremento modular de un registro qubit por una constante de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="9e35e-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9e35e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e35e-106">Description</span></span>

<span data-ttu-id="9e35e-107">Vamos `increment` a indicar $a $, `modulus` $N $ y un entero codificados en `target` por $y $.</span><span class="sxs-lookup"><span data-stu-id="9e35e-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="9e35e-108">A continuación, la operación realiza la transformación siguiente: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} los enteros se codifican en formato Little-endian en base QFT.</span><span class="sxs-lookup"><span data-stu-id="9e35e-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="9e35e-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="9e35e-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="9e35e-110">incremento: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9e35e-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9e35e-111">Incremento de entero $a $ que se va a agregar a $y $.</span><span class="sxs-lookup"><span data-stu-id="9e35e-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="9e35e-112">módulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9e35e-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9e35e-113">Entero $N $ que mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="9e35e-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="9e35e-114">destino: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9e35e-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="9e35e-115">Entero $y $ en formato Little-endian con codificación en fases `increment` al que se agrega $a $.</span><span class="sxs-lookup"><span data-stu-id="9e35e-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9e35e-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e35e-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9e35e-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9e35e-117">Remarks</span></span>

<span data-ttu-id="9e35e-118">Supone que `target` tiene el bit más alto establecido en 0.</span><span class="sxs-lookup"><span data-stu-id="9e35e-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="9e35e-119">También se supone que el valor de destino es menor que $N $.</span><span class="sxs-lookup"><span data-stu-id="9e35e-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="9e35e-120">En el diagrama de circuitos y la explicación, vea la figura 5 de la [Página 5 de arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span><span class="sxs-lookup"><span data-stu-id="9e35e-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="9e35e-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9e35e-121">See Also</span></span>

- [<span data-ttu-id="9e35e-122">Microsoft. Quantum. aritmético. IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="9e35e-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)