---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operación MultiplyByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 080414d208a2a0c114857db8e93efb4cd74a4d8d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222582"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="da25e-102">Operación MultiplyByModularInteger</span><span class="sxs-lookup"><span data-stu-id="da25e-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="da25e-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="da25e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="da25e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da25e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da25e-105">Realiza una multiplicación modular por una constante de tipo entero en un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="da25e-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="da25e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="da25e-106">Description</span></span>

<span data-ttu-id="da25e-107">Díganos `modulus` $N $ y `constMultiplier` $a $.</span><span class="sxs-lookup"><span data-stu-id="da25e-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="da25e-108">Después, esta operación implementa una operación unitario definida por la siguiente asignación en la base de cálculo: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ para todos los $y $ entre $0 $ y $N-$1.</span><span class="sxs-lookup"><span data-stu-id="da25e-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="da25e-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="da25e-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="da25e-110">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da25e-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="da25e-111">Constante por la que se va a multiplicar el multiplicador.</span><span class="sxs-lookup"><span data-stu-id="da25e-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="da25e-112">Debe ser cofundador para el módulo.</span><span class="sxs-lookup"><span data-stu-id="da25e-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="da25e-113">módulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da25e-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="da25e-114">La operación de multiplicación se realiza en módulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="da25e-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="da25e-115">multiplicador: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="da25e-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="da25e-116">Número que se va a multiplicar por una constante.</span><span class="sxs-lookup"><span data-stu-id="da25e-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="da25e-117">Se trata de una matriz de qubits que codifica un entero en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="da25e-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="da25e-118">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da25e-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="da25e-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="da25e-119">Remarks</span></span>

- <span data-ttu-id="da25e-120">En el diagrama de circuitos y la explicación, consulte la figura 7 en la [Página 8 de arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="da25e-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="da25e-121">Esta operación corresponde a U ₐ en [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="da25e-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>