---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: Operación ApplyToRest
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: fe49361f3c2259960eaa58d47df9b69b30b572a8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208279"
---
# <a name="applytorest-operation"></a><span data-ttu-id="b151d-102">Operación ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="b151d-102">ApplyToRest operation</span></span>

<span data-ttu-id="b151d-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b151d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b151d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b151d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b151d-105">Aplica una operación a todo menos al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="b151d-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="b151d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b151d-106">Description</span></span>

<span data-ttu-id="b151d-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="b151d-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="b151d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="b151d-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="b151d-109">OP: ' t [] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="b151d-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b151d-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="b151d-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b151d-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="b151d-111">targets : 'T[]</span></span>

<span data-ttu-id="b151d-112">Matriz de destinos, de la que se aplicarán todos los, excepto el primero `op` .</span><span class="sxs-lookup"><span data-stu-id="b151d-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b151d-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b151d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b151d-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="b151d-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b151d-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="b151d-115">'T</span></span>

<span data-ttu-id="b151d-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="b151d-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b151d-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b151d-117">See Also</span></span>

- [<span data-ttu-id="b151d-118">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="b151d-118">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="b151d-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="b151d-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="b151d-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="b151d-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)