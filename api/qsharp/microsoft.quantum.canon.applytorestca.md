---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: Operación ApplyToRestCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: e64eeaae2151a28c289e3e71e47f897d6c378b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841238"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="45f37-102">Operación ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="45f37-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="45f37-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="45f37-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="45f37-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45f37-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45f37-105">Aplica una operación a todo menos al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="45f37-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="45f37-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="45f37-106">Description</span></span>

<span data-ttu-id="45f37-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="45f37-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="45f37-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="45f37-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="45f37-109">OP: ' t [] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="45f37-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="45f37-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="45f37-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="45f37-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="45f37-111">targets : 'T[]</span></span>

<span data-ttu-id="45f37-112">Matriz de destinos, de la que se aplicarán todos los, excepto el primero `op` .</span><span class="sxs-lookup"><span data-stu-id="45f37-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45f37-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45f37-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="45f37-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="45f37-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="45f37-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="45f37-115">'T</span></span>

<span data-ttu-id="45f37-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="45f37-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="45f37-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45f37-117">See Also</span></span>

- [<span data-ttu-id="45f37-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="45f37-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="45f37-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="45f37-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="45f37-120">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="45f37-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)