---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: Operación ApplyIfCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b0ac469d6dea51951e0d9b2cfceb54253d4b4c5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209628"
---
# <a name="applyifca-operation"></a><span data-ttu-id="f34e6-102">Operación ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="f34e6-102">ApplyIfCA operation</span></span>

<span data-ttu-id="f34e6-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f34e6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f34e6-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f34e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f34e6-105">Aplica una operación de unitario condicionada en un bit clásico.</span><span class="sxs-lookup"><span data-stu-id="f34e6-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f34e6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f34e6-106">Description</span></span>

<span data-ttu-id="f34e6-107">Dada una operación `op` y un valor de bit `bit` , se aplica `op` a `target` si `bit` es `true` .</span><span class="sxs-lookup"><span data-stu-id="f34e6-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="f34e6-108">Si es `false` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="f34e6-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="f34e6-109">El sufijo `CA` indica que la operación que se va a aplicar es la unitario (controlable y adjointable).</span><span class="sxs-lookup"><span data-stu-id="f34e6-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="f34e6-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="f34e6-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="f34e6-111">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f34e6-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f34e6-112">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="f34e6-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="f34e6-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f34e6-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f34e6-114">un valor booleano que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="f34e6-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="f34e6-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="f34e6-115">target : 'T</span></span>

<span data-ttu-id="f34e6-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="f34e6-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f34e6-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f34e6-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f34e6-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="f34e6-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f34e6-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="f34e6-119">'T</span></span>

<span data-ttu-id="f34e6-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="f34e6-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f34e6-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f34e6-121">See Also</span></span>

- [<span data-ttu-id="f34e6-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="f34e6-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="f34e6-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="f34e6-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="f34e6-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="f34e6-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)