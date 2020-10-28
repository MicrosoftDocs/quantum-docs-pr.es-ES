---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Operación ApplyIf
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729597"
---
# <a name="applyif-operation"></a><span data-ttu-id="05591-102">Operación ApplyIf</span><span class="sxs-lookup"><span data-stu-id="05591-102">ApplyIf operation</span></span>

<span data-ttu-id="05591-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="05591-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="05591-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05591-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05591-105">Aplica una operación condicionada en un bit clásico.</span><span class="sxs-lookup"><span data-stu-id="05591-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="05591-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="05591-106">Description</span></span>

<span data-ttu-id="05591-107">Dada una operación `op` y un valor de bit `bit` , se aplica `op` a `target` si `bit` es `true` .</span><span class="sxs-lookup"><span data-stu-id="05591-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="05591-108">Si es `false` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="05591-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="05591-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="05591-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="05591-110">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="05591-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="05591-111">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="05591-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="05591-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="05591-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="05591-113">un valor booleano que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="05591-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="05591-114">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="05591-114">target : 'T</span></span>

<span data-ttu-id="05591-115">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="05591-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05591-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05591-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="05591-117">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="05591-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="05591-118">Traslada</span><span class="sxs-lookup"><span data-stu-id="05591-118">'T</span></span>

<span data-ttu-id="05591-119">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="05591-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="05591-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05591-120">See Also</span></span>

- [<span data-ttu-id="05591-121">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="05591-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="05591-122">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="05591-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="05591-123">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="05591-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)