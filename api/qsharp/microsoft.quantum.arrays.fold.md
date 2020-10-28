---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730244"
---
# <a name="fold-function"></a><span data-ttu-id="2bd41-102">Fold (función)</span><span class="sxs-lookup"><span data-stu-id="2bd41-102">Fold function</span></span>

<span data-ttu-id="2bd41-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2bd41-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2bd41-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2bd41-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2bd41-105">Recorre en iteración una función `f` a través de una matriz `array` y devuelve `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="2bd41-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="2bd41-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2bd41-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="2bd41-107">carpeta: (' State, ')-> ' estado</span><span class="sxs-lookup"><span data-stu-id="2bd41-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="2bd41-108">Función que se va a doblar en la matriz.</span><span class="sxs-lookup"><span data-stu-id="2bd41-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="2bd41-109">Estado: ' estado '</span><span class="sxs-lookup"><span data-stu-id="2bd41-109">state : 'State</span></span>

<span data-ttu-id="2bd41-110">Estado inicial de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="2bd41-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="2bd41-111">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="2bd41-111">array : 'T[]</span></span>

<span data-ttu-id="2bd41-112">Matriz de valores que se van a plegar.</span><span class="sxs-lookup"><span data-stu-id="2bd41-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="2bd41-113">Salida: ' estado</span><span class="sxs-lookup"><span data-stu-id="2bd41-113">Output : 'State</span></span>

<span data-ttu-id="2bd41-114">Estado final devuelto por la carpeta después de recorrer en iteración todos los elementos de `array` .</span><span class="sxs-lookup"><span data-stu-id="2bd41-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2bd41-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2bd41-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="2bd41-116">' Estado</span><span class="sxs-lookup"><span data-stu-id="2bd41-116">'State</span></span>

<span data-ttu-id="2bd41-117">El tipo de Estados `folder` en que funciona la función, es decir, acepta como primer argumento y devuelve.</span><span class="sxs-lookup"><span data-stu-id="2bd41-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="2bd41-118">Traslada</span><span class="sxs-lookup"><span data-stu-id="2bd41-118">'T</span></span>

<span data-ttu-id="2bd41-119">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="2bd41-119">The type of `array` elements.</span></span>