---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: Operación ApplyToRestC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 779c3831b2027a58f97dae9609e96d4d98247da7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208200"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="35b30-102">Operación ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="35b30-102">ApplyToRestC operation</span></span>

<span data-ttu-id="35b30-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="35b30-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="35b30-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35b30-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35b30-105">Aplica una operación a todo menos al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="35b30-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="35b30-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="35b30-106">Description</span></span>

<span data-ttu-id="35b30-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="35b30-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="35b30-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="35b30-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="35b30-109">OP: ' t [] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="35b30-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="35b30-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="35b30-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="35b30-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="35b30-111">targets : 'T[]</span></span>

<span data-ttu-id="35b30-112">Matriz de destinos, de la que se aplicarán todos los, excepto el primero `op` .</span><span class="sxs-lookup"><span data-stu-id="35b30-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="35b30-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35b30-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="35b30-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="35b30-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35b30-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="35b30-115">'T</span></span>

<span data-ttu-id="35b30-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="35b30-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="35b30-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35b30-117">See Also</span></span>

- [<span data-ttu-id="35b30-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="35b30-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="35b30-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="35b30-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="35b30-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="35b30-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)