---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: Operación ApplyIfC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: e16254154909eb844164538acb7b82fedc11f86a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729596"
---
# <a name="applyifc-operation"></a><span data-ttu-id="f8510-102">Operación ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="f8510-102">ApplyIfC operation</span></span>

<span data-ttu-id="f8510-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f8510-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f8510-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f8510-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f8510-105">Aplica una operación controlable condicionada en un bit clásico.</span><span class="sxs-lookup"><span data-stu-id="f8510-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="f8510-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8510-106">Description</span></span>

<span data-ttu-id="f8510-107">Dada una operación `op` y un valor de bit `bit` , se aplica `op` a `target` si `bit` es `true` .</span><span class="sxs-lookup"><span data-stu-id="f8510-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="f8510-108">Si es `false` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="f8510-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="f8510-109">El sufijo `C` indica que la operación que se va a aplicar es controlable.</span><span class="sxs-lookup"><span data-stu-id="f8510-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="f8510-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="f8510-110">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="f8510-111">OP: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8510-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f8510-112">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="f8510-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="f8510-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f8510-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f8510-114">un valor booleano que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="f8510-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="f8510-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="f8510-115">target : 'T</span></span>

<span data-ttu-id="f8510-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="f8510-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f8510-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8510-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f8510-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="f8510-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f8510-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="f8510-119">'T</span></span>

<span data-ttu-id="f8510-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="f8510-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8510-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8510-121">See Also</span></span>

- [<span data-ttu-id="f8510-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="f8510-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="f8510-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="f8510-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="f8510-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="f8510-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)