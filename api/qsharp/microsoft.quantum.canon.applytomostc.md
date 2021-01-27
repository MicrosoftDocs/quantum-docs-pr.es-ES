---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Operación ApplyToMostC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 14de9f367aa7d19f64f13186d402239ae1fef3c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850552"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="8f71c-102">Operación ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="8f71c-102">ApplyToMostC operation</span></span>

<span data-ttu-id="8f71c-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8f71c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8f71c-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f71c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f71c-105">Aplica una operación a todo menos al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="8f71c-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="8f71c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f71c-106">Description</span></span>

<span data-ttu-id="8f71c-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="8f71c-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="8f71c-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="8f71c-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="8f71c-109">OP: ' t [] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="8f71c-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8f71c-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="8f71c-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="8f71c-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="8f71c-111">targets : 'T[]</span></span>

<span data-ttu-id="8f71c-112">Matriz de destinos, de la que se aplicarán todos los, excepto el último `op` .</span><span class="sxs-lookup"><span data-stu-id="8f71c-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f71c-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f71c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8f71c-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="8f71c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f71c-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="8f71c-115">'T</span></span>

<span data-ttu-id="8f71c-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="8f71c-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f71c-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f71c-117">See Also</span></span>

- [<span data-ttu-id="8f71c-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="8f71c-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="8f71c-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="8f71c-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="8f71c-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="8f71c-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)