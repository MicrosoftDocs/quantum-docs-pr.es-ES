---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Operación ApplyIfA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: d2880bbb95ebaf621ef9e5885051b94f32a3f1cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218774"
---
# <a name="applyifa-operation"></a><span data-ttu-id="7cb99-102">Operación ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="7cb99-102">ApplyIfA operation</span></span>

<span data-ttu-id="7cb99-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7cb99-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7cb99-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7cb99-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7cb99-105">Aplica una operación adjointable condicionada en un bit clásico.</span><span class="sxs-lookup"><span data-stu-id="7cb99-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="7cb99-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7cb99-106">Description</span></span>

<span data-ttu-id="7cb99-107">Dada una operación `op` y un valor de bit `bit` , se aplica `op` a `target` si `bit` es `true` .</span><span class="sxs-lookup"><span data-stu-id="7cb99-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="7cb99-108">Si es `false` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="7cb99-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="7cb99-109">El sufijo `A` indica que la operación que se va a aplicar es adjointable.</span><span class="sxs-lookup"><span data-stu-id="7cb99-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="7cb99-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="7cb99-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="7cb99-111">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="7cb99-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7cb99-112">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="7cb99-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="7cb99-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7cb99-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7cb99-114">un valor booleano que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="7cb99-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="7cb99-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="7cb99-115">target : 'T</span></span>

<span data-ttu-id="7cb99-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="7cb99-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7cb99-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7cb99-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7cb99-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="7cb99-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7cb99-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="7cb99-119">'T</span></span>

<span data-ttu-id="7cb99-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="7cb99-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7cb99-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7cb99-121">See Also</span></span>

- [<span data-ttu-id="7cb99-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="7cb99-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="7cb99-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="7cb99-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="7cb99-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="7cb99-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)