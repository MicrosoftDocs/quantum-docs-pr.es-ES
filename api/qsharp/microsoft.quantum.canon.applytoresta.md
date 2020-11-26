---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: Operación ApplyToRestA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 34cb5071dd939d0831e39bb8f1670670ae1fad31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208316"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="71e43-102">Operación ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="71e43-102">ApplyToRestA operation</span></span>

<span data-ttu-id="71e43-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71e43-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71e43-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71e43-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71e43-105">Aplica una operación a todo menos al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="71e43-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="71e43-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="71e43-106">Description</span></span>

<span data-ttu-id="71e43-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="71e43-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="71e43-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="71e43-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="71e43-109">OP: ' t [] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="71e43-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="71e43-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="71e43-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="71e43-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="71e43-111">targets : 'T[]</span></span>

<span data-ttu-id="71e43-112">Matriz de destinos, de la que se aplicarán todos los, excepto el primero `op` .</span><span class="sxs-lookup"><span data-stu-id="71e43-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71e43-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71e43-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="71e43-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="71e43-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71e43-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="71e43-115">'T</span></span>

<span data-ttu-id="71e43-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="71e43-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="71e43-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71e43-117">See Also</span></span>

- [<span data-ttu-id="71e43-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="71e43-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="71e43-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="71e43-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="71e43-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="71e43-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)