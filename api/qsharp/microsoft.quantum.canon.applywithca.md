---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: Operación ApplyWithCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: e86c452e9693c5a4d0d4e5a36471ab46bbf66dfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208149"
---
# <a name="applywithca-operation"></a><span data-ttu-id="962ec-102">Operación ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="962ec-102">ApplyWithCA operation</span></span>

<span data-ttu-id="962ec-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="962ec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="962ec-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="962ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="962ec-105">Dadas dos operaciones, se aplica una como conjugada con la otra.</span><span class="sxs-lookup"><span data-stu-id="962ec-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="962ec-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="962ec-106">Description</span></span>

<span data-ttu-id="962ec-107">Dadas dos operaciones, que se describen respectivamente por los operadores unitarios $U $ y $V $, se aplican en la secuencia $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="962ec-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="962ec-108">Es decir, esta operación implementa el operador unitario proporcionado por $V $ conjugado con $U $.</span><span class="sxs-lookup"><span data-stu-id="962ec-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="962ec-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="962ec-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="962ec-110">outerOperation: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="962ec-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="962ec-111">La operación $U $ que se debe usar para conjugado $V $.</span><span class="sxs-lookup"><span data-stu-id="962ec-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="962ec-112">Tenga en cuenta que la operación exterior $U $ debe ser adjointable, pero no es necesario que sea controlable.</span><span class="sxs-lookup"><span data-stu-id="962ec-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj--ctl"></a><span data-ttu-id="962ec-113">innerOperation: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="962ec-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="962ec-114">Operación $V $ que se va a conjugado.</span><span class="sxs-lookup"><span data-stu-id="962ec-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="962ec-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="962ec-115">target : 'T</span></span>

<span data-ttu-id="962ec-116">Entrada que se va a proporcionar a las operaciones externas e internas.</span><span class="sxs-lookup"><span data-stu-id="962ec-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="962ec-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="962ec-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="962ec-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="962ec-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="962ec-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="962ec-119">'T</span></span>

<span data-ttu-id="962ec-120">Destino en el que actúa cada una de las operaciones internas y externas.</span><span class="sxs-lookup"><span data-stu-id="962ec-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="962ec-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="962ec-121">Remarks</span></span>

<span data-ttu-id="962ec-122">La operación exterior siempre se supone que es adjointable, pero no es necesario que se pueda controlar para que la operación combinada sea controlable.</span><span class="sxs-lookup"><span data-stu-id="962ec-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="962ec-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="962ec-123">See Also</span></span>

- [<span data-ttu-id="962ec-124">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="962ec-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="962ec-125">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="962ec-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="962ec-126">Microsoft. Quantum. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="962ec-126">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)