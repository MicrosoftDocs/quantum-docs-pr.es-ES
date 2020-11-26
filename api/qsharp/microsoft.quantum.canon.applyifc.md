---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: Operación ApplyIfC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: 35430cb7cf491965b7b69ace6d3f41599dbadd51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218723"
---
# <a name="applyifc-operation"></a><span data-ttu-id="3a4dc-102">Operación ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="3a4dc-102">ApplyIfC operation</span></span>

<span data-ttu-id="3a4dc-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3a4dc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3a4dc-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3a4dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3a4dc-105">Aplica una operación controlable condicionada en un bit clásico.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="3a4dc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a4dc-106">Description</span></span>

<span data-ttu-id="3a4dc-107">Dada una operación `op` y un valor de bit `bit` , se aplica `op` a `target` si `bit` es `true` .</span><span class="sxs-lookup"><span data-stu-id="3a4dc-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="3a4dc-108">Si es `false` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="3a4dc-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="3a4dc-109">El sufijo `C` indica que la operación que se va a aplicar es controlable.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="3a4dc-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="3a4dc-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="3a4dc-111">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="3a4dc-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3a4dc-112">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="3a4dc-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3a4dc-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3a4dc-114">un valor booleano que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="3a4dc-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="3a4dc-115">target : 'T</span></span>

<span data-ttu-id="3a4dc-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3a4dc-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3a4dc-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3a4dc-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="3a4dc-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3a4dc-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="3a4dc-119">'T</span></span>

<span data-ttu-id="3a4dc-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a4dc-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a4dc-121">See Also</span></span>

- [<span data-ttu-id="3a4dc-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="3a4dc-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="3a4dc-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="3a4dc-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="3a4dc-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="3a4dc-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)