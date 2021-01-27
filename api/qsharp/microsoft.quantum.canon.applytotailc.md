---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: Operación ApplyToTailC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 8408dff24c5c57efbedb649ac182fac49e836a3e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850428"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="bdadd-102">Operación ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="bdadd-102">ApplyToTailC operation</span></span>

<span data-ttu-id="bdadd-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bdadd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bdadd-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bdadd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bdadd-105">Aplica una operación al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="bdadd-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="bdadd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdadd-106">Description</span></span>

<span data-ttu-id="bdadd-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="bdadd-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="bdadd-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="bdadd-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="bdadd-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="bdadd-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bdadd-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="bdadd-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="bdadd-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="bdadd-111">targets : 'T[]</span></span>

<span data-ttu-id="bdadd-112">Matriz de destinos, de la que se aplicará el último `op` .</span><span class="sxs-lookup"><span data-stu-id="bdadd-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bdadd-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bdadd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bdadd-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="bdadd-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bdadd-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="bdadd-115">'T</span></span>

<span data-ttu-id="bdadd-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="bdadd-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdadd-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bdadd-117">See Also</span></span>

- [<span data-ttu-id="bdadd-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="bdadd-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="bdadd-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="bdadd-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="bdadd-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="bdadd-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)