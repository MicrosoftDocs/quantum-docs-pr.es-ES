---
uid: Microsoft.Quantum.Arrays.Swapped
title: Swapd (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729988"
---
# <a name="swapped-function"></a><span data-ttu-id="f5485-102">Swapd (función)</span><span class="sxs-lookup"><span data-stu-id="f5485-102">Swapped function</span></span>

<span data-ttu-id="f5485-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f5485-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f5485-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5485-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5485-105">Aplica un intercambio de dos elementos en una matriz.</span><span class="sxs-lookup"><span data-stu-id="f5485-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f5485-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f5485-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="f5485-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f5485-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f5485-108">Índice del primer elemento que se va a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="f5485-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="f5485-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f5485-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f5485-110">Índice del segundo elemento que se va a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="f5485-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="f5485-111">ARR: ' t []</span><span class="sxs-lookup"><span data-stu-id="f5485-111">arr : 'T[]</span></span>

<span data-ttu-id="f5485-112">Matriz con los elementos que se van a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="f5485-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="f5485-113">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="f5485-113">Output : 'T[]</span></span>

<span data-ttu-id="f5485-114">Matriz con el intercambio en contexto aplicado.</span><span class="sxs-lookup"><span data-stu-id="f5485-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="f5485-115">Ejemplo: </span><span class="sxs-lookup"><span data-stu-id="f5485-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="f5485-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="f5485-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f5485-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="f5485-117">'T</span></span>

