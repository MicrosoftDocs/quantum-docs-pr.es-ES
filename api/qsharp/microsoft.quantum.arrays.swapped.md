---
uid: Microsoft.Quantum.Arrays.Swapped
title: Swapd (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 173fb32b5a41ce054f19548a7fcca18c11c4c4cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220134"
---
# <a name="swapped-function"></a><span data-ttu-id="3420e-102">Swapd (función)</span><span class="sxs-lookup"><span data-stu-id="3420e-102">Swapped function</span></span>

<span data-ttu-id="3420e-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3420e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3420e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3420e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3420e-105">Aplica un intercambio de dos elementos en una matriz.</span><span class="sxs-lookup"><span data-stu-id="3420e-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="3420e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3420e-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="3420e-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3420e-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3420e-108">Índice del primer elemento que se va a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="3420e-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="3420e-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3420e-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3420e-110">Índice del segundo elemento que se va a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="3420e-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="3420e-111">ARR: ' t []</span><span class="sxs-lookup"><span data-stu-id="3420e-111">arr : 'T[]</span></span>

<span data-ttu-id="3420e-112">Matriz con los elementos que se van a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="3420e-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="3420e-113">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="3420e-113">Output : 'T[]</span></span>

<span data-ttu-id="3420e-114">Matriz con el intercambio en contexto aplicado.</span><span class="sxs-lookup"><span data-stu-id="3420e-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="3420e-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3420e-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="3420e-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="3420e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3420e-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="3420e-117">'T</span></span>

