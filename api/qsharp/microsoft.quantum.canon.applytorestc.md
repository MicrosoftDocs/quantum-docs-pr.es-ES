---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: Operación ApplyToRestC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 1e533a9f0994b70054aeca2f9ddd97f4e200b03f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850488"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="88b9f-102">Operación ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="88b9f-102">ApplyToRestC operation</span></span>

<span data-ttu-id="88b9f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="88b9f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="88b9f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88b9f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88b9f-105">Aplica una operación a todo menos al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="88b9f-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="88b9f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="88b9f-106">Description</span></span>

<span data-ttu-id="88b9f-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="88b9f-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="88b9f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="88b9f-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="88b9f-109">OP: ' t [] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="88b9f-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="88b9f-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="88b9f-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="88b9f-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="88b9f-111">targets : 'T[]</span></span>

<span data-ttu-id="88b9f-112">Matriz de destinos, de la que se aplicarán todos los, excepto el primero `op` .</span><span class="sxs-lookup"><span data-stu-id="88b9f-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="88b9f-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="88b9f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="88b9f-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="88b9f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="88b9f-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="88b9f-115">'T</span></span>

<span data-ttu-id="88b9f-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="88b9f-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="88b9f-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88b9f-117">See Also</span></span>

- [<span data-ttu-id="88b9f-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="88b9f-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="88b9f-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="88b9f-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="88b9f-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="88b9f-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)