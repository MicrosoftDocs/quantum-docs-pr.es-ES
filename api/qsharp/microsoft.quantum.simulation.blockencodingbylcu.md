---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 1d7890e96513817c127ef768f49c0b915ea22fa1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858158"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="f146f-102">BlockEncodingByLCU función)</span><span class="sxs-lookup"><span data-stu-id="f146f-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="f146f-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f146f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f146f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f146f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f146f-105">Codifica un operador de interés en un `BlockEncoding` .</span><span class="sxs-lookup"><span data-stu-id="f146f-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="f146f-106">Esto crea una `BlockEncoding` $U unitario = P\cdot V\cdot P ^ \dagger $ que codifica algún operador $H = \ sum_ {j} | \ alpha_j | U_j $ de interés que es una combinación lineal de unitaries.</span><span class="sxs-lookup"><span data-stu-id="f146f-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="f146f-107">Normalmente, $P $ es una unitario de preparación de estado de forma que $P \ket {0} \_ a = \ sum_j \vec\alpha alpha_j \sqrt{\/ \| \| \_ 2} \ket{j} \_ a $ y $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="f146f-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="f146f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f146f-108">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="f146f-109">statePreparation: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f146f-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f146f-110">$P unitario $ que prepara algún Estado de destino.</span><span class="sxs-lookup"><span data-stu-id="f146f-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="f146f-111">Selector: (' t, ') => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f146f-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f146f-112">$V unitario $ que codifica el componente unitaries de $H $.</span><span class="sxs-lookup"><span data-stu-id="f146f-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit--is-adj--ctl"></a><span data-ttu-id="f146f-113">Output: (' t, ') => [Unit](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f146f-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f146f-114">Una unidad $U $ actuando conjuntamente en los registros `a` y `s` que codifica en bloque $H $ y cumple $U ^ \Dagger = U $.</span><span class="sxs-lookup"><span data-stu-id="f146f-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f146f-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="f146f-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f146f-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="f146f-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="f146f-117">Hoy</span><span class="sxs-lookup"><span data-stu-id="f146f-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="f146f-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f146f-118">Remarks</span></span>

<span data-ttu-id="f146f-119">Esta `BlockEncoding` implementación proporciona las propiedades de un `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="f146f-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f146f-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f146f-120">See Also</span></span>

- [<span data-ttu-id="f146f-121">Microsoft. Quantum. Simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="f146f-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="f146f-122">Microsoft. Quantum. Simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="f146f-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)