---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: ConjugatedByA función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 141c42d335add85103e16598264f781f32ab80fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840849"
---
# <a name="conjugatedbya-function"></a><span data-ttu-id="39d96-102">ConjugatedByA función)</span><span class="sxs-lookup"><span data-stu-id="39d96-102">ConjugatedByA function</span></span>

<span data-ttu-id="39d96-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39d96-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39d96-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39d96-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39d96-105">Dadas las operaciones externas e internas, devuelve una nueva operación que conjuga la operación interna mediante la operación externa.</span><span class="sxs-lookup"><span data-stu-id="39d96-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="39d96-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="39d96-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="39d96-107">outerOperation: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="39d96-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="39d96-108">La operación $U $ que se debe usar para conjugado $V $.</span><span class="sxs-lookup"><span data-stu-id="39d96-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="39d96-109">Tenga en cuenta que la operación exterior $U $ debe ser adjointable, pero no es necesario que sea controlable.</span><span class="sxs-lookup"><span data-stu-id="39d96-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj"></a><span data-ttu-id="39d96-110">innerOperation: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="39d96-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="39d96-111">Operación $V $ que se va a conjugado.</span><span class="sxs-lookup"><span data-stu-id="39d96-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="39d96-112">Salida: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="39d96-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="39d96-113">Nueva operación cuya acción está representada por la unidad de $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="39d96-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="39d96-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="39d96-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39d96-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="39d96-115">'T</span></span>

<span data-ttu-id="39d96-116">Tipo del destino en el que actúa cada una de las operaciones internas y externas.</span><span class="sxs-lookup"><span data-stu-id="39d96-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="39d96-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="39d96-117">Remarks</span></span>

<span data-ttu-id="39d96-118">La operación exterior siempre se supone que es adjointable, pero no es necesario que se pueda controlar para que la operación combinada sea controlable.</span><span class="sxs-lookup"><span data-stu-id="39d96-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="39d96-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39d96-119">See Also</span></span>

- [<span data-ttu-id="39d96-120">Microsoft. Quantum. Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="39d96-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="39d96-121">Microsoft. Quantum. Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="39d96-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="39d96-122">Microsoft. Quantum. Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="39d96-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="39d96-123">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="39d96-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)