---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: Operación MultiplyAndAddByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 3f85f6aaea1d6f8095709c6f387322df7a5e047c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730644"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="6716f-102">Operación MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="6716f-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="6716f-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6716f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6716f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6716f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6716f-105">Realiza una multiplicación modular y agrega una constante de tipo entero en un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="6716f-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="6716f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6716f-106">Description</span></span>

<span data-ttu-id="6716f-107">Implementa el mapa $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ para un módulo determinado $N $, multiplicador constante $a $ y sumando $y $.</span><span class="sxs-lookup"><span data-stu-id="6716f-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="6716f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="6716f-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="6716f-109">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6716f-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6716f-110">Entero $a $ que se va a agregar a cada etiqueta de estado de base.</span><span class="sxs-lookup"><span data-stu-id="6716f-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="6716f-111">módulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6716f-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6716f-112">El módulo $N $ que se toma la suma y la multiplicación con respecto a.</span><span class="sxs-lookup"><span data-stu-id="6716f-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="6716f-113">multiplicador: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6716f-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6716f-114">Un registro de Quantum que representa un entero sin signo cuyo valor se va a agregar a cada etiqueta de estado de base de `summand` .</span><span class="sxs-lookup"><span data-stu-id="6716f-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="6716f-115">sumando: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6716f-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6716f-116">Un registro de Quantum que representa un entero sin signo que se va a usar como destino para esta operación.</span><span class="sxs-lookup"><span data-stu-id="6716f-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6716f-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6716f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6716f-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6716f-118">Remarks</span></span>

- <span data-ttu-id="6716f-119">En el diagrama de circuitos y la explicación, consulte la figura 6 de la [Página 7 de arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span><span class="sxs-lookup"><span data-stu-id="6716f-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="6716f-120">Esta operación corresponde a CMULT (a) MOD (N) en [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="6716f-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="6716f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6716f-121">See Also</span></span>

- [<span data-ttu-id="6716f-122">Microsoft. Quantum. aritmético. MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="6716f-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)