---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730365"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="4a656-102">CumulativeFolded función)</span><span class="sxs-lookup"><span data-stu-id="4a656-102">CumulativeFolded function</span></span>

<span data-ttu-id="4a656-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4a656-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4a656-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a656-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a656-105">Combina asignaciones y pliegues en una sola función</span><span class="sxs-lookup"><span data-stu-id="4a656-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="4a656-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a656-106">Description</span></span>

<span data-ttu-id="4a656-107">Esta función recorre en iteración la `fn` función a través de la matriz, empezando por un estado inicial `state` y devuelve todos los valores intermedios, sin incluir el estado inicial.</span><span class="sxs-lookup"><span data-stu-id="4a656-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="4a656-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="4a656-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="4a656-109">FN: (' State, ')-> ' estado</span><span class="sxs-lookup"><span data-stu-id="4a656-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="4a656-110">Función que se va a doblar en la matriz.</span><span class="sxs-lookup"><span data-stu-id="4a656-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="4a656-111">Estado: ' estado '</span><span class="sxs-lookup"><span data-stu-id="4a656-111">state : 'State</span></span>

<span data-ttu-id="4a656-112">Estado inicial que se va a doblar</span><span class="sxs-lookup"><span data-stu-id="4a656-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="4a656-113">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="4a656-113">array : 'T[]</span></span>

<span data-ttu-id="4a656-114">Matriz de valores que se van a doblar</span><span class="sxs-lookup"><span data-stu-id="4a656-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="4a656-115">Salida: ' estado []</span><span class="sxs-lookup"><span data-stu-id="4a656-115">Output : 'State[]</span></span>

<span data-ttu-id="4a656-116">Todos los Estados intermedios, incluido el estado final, pero no el estado inicial.</span><span class="sxs-lookup"><span data-stu-id="4a656-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="4a656-117">La longitud de la matriz de salida tiene la misma longitud que `array` .</span><span class="sxs-lookup"><span data-stu-id="4a656-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4a656-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="4a656-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="4a656-119">' Estado</span><span class="sxs-lookup"><span data-stu-id="4a656-119">'State</span></span>

<span data-ttu-id="4a656-120">El tipo de Estados en que `fn` funciona la función, es decir, acepta como primera entrada y devuelve.</span><span class="sxs-lookup"><span data-stu-id="4a656-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="4a656-121">Traslada</span><span class="sxs-lookup"><span data-stu-id="4a656-121">'T</span></span>

<span data-ttu-id="4a656-122">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="4a656-122">The type of `array` elements.</span></span>