---
uid: Microsoft.Quantum.Arrays.Swapped
title: Swapd (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850947"
---
# <a name="swapped-function"></a><span data-ttu-id="d7780-102">Swapd (función)</span><span class="sxs-lookup"><span data-stu-id="d7780-102">Swapped function</span></span>

<span data-ttu-id="d7780-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d7780-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d7780-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d7780-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d7780-105">Aplica un intercambio de dos elementos en una matriz.</span><span class="sxs-lookup"><span data-stu-id="d7780-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d7780-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d7780-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="d7780-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7780-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d7780-108">Índice del primer elemento que se va a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="d7780-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="d7780-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7780-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d7780-110">Índice del segundo elemento que se va a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="d7780-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="d7780-111">ARR: ' t []</span><span class="sxs-lookup"><span data-stu-id="d7780-111">arr : 'T[]</span></span>

<span data-ttu-id="d7780-112">Matriz con los elementos que se van a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="d7780-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="d7780-113">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="d7780-113">Output : 'T[]</span></span>

<span data-ttu-id="d7780-114">Matriz con el intercambio en contexto aplicado.</span><span class="sxs-lookup"><span data-stu-id="d7780-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="d7780-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d7780-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="d7780-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d7780-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d7780-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="d7780-117">'T</span></span>

