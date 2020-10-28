---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: Operación ApplyWithCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: abc62791416e78c1b2937a226327b71da8b8e288
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729008"
---
# <a name="applywithca-operation"></a><span data-ttu-id="0e340-102">Operación ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="0e340-102">ApplyWithCA operation</span></span>

<span data-ttu-id="0e340-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0e340-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0e340-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e340-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e340-105">Dadas dos operaciones, se aplica una como conjugada con la otra.</span><span class="sxs-lookup"><span data-stu-id="0e340-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="0e340-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e340-106">Description</span></span>

<span data-ttu-id="0e340-107">Dadas dos operaciones, que se describen respectivamente por los operadores unitarios $U $ y $V $, se aplican en la secuencia $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="0e340-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="0e340-108">Es decir, esta operación implementa el operador unitario proporcionado por $V $ conjugado con $U $.</span><span class="sxs-lookup"><span data-stu-id="0e340-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="0e340-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="0e340-109">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="0e340-110">outerOperation: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e340-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="0e340-111">La operación $U $ que se debe usar para conjugado $V $.</span><span class="sxs-lookup"><span data-stu-id="0e340-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="0e340-112">Tenga en cuenta que la operación exterior $U $ debe ser adjointable, pero no es necesario que sea controlable.</span><span class="sxs-lookup"><span data-stu-id="0e340-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-adj--ctl"></a><span data-ttu-id="0e340-113">innerOperation: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="0e340-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0e340-114">Operación $V $ que se va a conjugado.</span><span class="sxs-lookup"><span data-stu-id="0e340-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="0e340-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="0e340-115">target : 'T</span></span>

<span data-ttu-id="0e340-116">Entrada que se va a proporcionar a las operaciones externas e internas.</span><span class="sxs-lookup"><span data-stu-id="0e340-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e340-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e340-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0e340-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="0e340-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0e340-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="0e340-119">'T</span></span>

<span data-ttu-id="0e340-120">Destino en el que actúa cada una de las operaciones internas y externas.</span><span class="sxs-lookup"><span data-stu-id="0e340-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e340-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0e340-121">Remarks</span></span>

<span data-ttu-id="0e340-122">La operación exterior siempre se supone que es adjointable, pero no es necesario que se pueda controlar para que la operación combinada sea controlable.</span><span class="sxs-lookup"><span data-stu-id="0e340-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e340-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e340-123">See Also</span></span>

- [<span data-ttu-id="0e340-124">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="0e340-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="0e340-125">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="0e340-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="0e340-126">Microsoft. Quantum. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="0e340-126">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)