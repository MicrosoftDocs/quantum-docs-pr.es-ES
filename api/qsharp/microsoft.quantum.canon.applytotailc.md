---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: Operación ApplyToTailC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 631e08666002d8077c6f8b78525b06b104dd4c7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729044"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="33eed-102">Operación ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="33eed-102">ApplyToTailC operation</span></span>

<span data-ttu-id="33eed-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="33eed-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="33eed-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33eed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33eed-105">Aplica una operación al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="33eed-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="33eed-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="33eed-106">Description</span></span>

<span data-ttu-id="33eed-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="33eed-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="33eed-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="33eed-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="33eed-109">OP: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33eed-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="33eed-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="33eed-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="33eed-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="33eed-111">targets : 'T[]</span></span>

<span data-ttu-id="33eed-112">Matriz de destinos, de la que se aplicará el último `op` .</span><span class="sxs-lookup"><span data-stu-id="33eed-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33eed-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33eed-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="33eed-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="33eed-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="33eed-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="33eed-115">'T</span></span>

<span data-ttu-id="33eed-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="33eed-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="33eed-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33eed-117">See Also</span></span>

- [<span data-ttu-id="33eed-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="33eed-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="33eed-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="33eed-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="33eed-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="33eed-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)