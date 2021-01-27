---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848602"
---
# <a name="fold-function"></a><span data-ttu-id="ee656-102">Fold (función)</span><span class="sxs-lookup"><span data-stu-id="ee656-102">Fold function</span></span>

<span data-ttu-id="ee656-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ee656-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ee656-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee656-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee656-105">Recorre en iteración una función `f` a través de una matriz `array` y devuelve `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="ee656-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="ee656-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ee656-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="ee656-107">carpeta: (' State, ')-> ' estado</span><span class="sxs-lookup"><span data-stu-id="ee656-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="ee656-108">Función que se va a doblar en la matriz.</span><span class="sxs-lookup"><span data-stu-id="ee656-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="ee656-109">Estado: ' estado '</span><span class="sxs-lookup"><span data-stu-id="ee656-109">state : 'State</span></span>

<span data-ttu-id="ee656-110">Estado inicial de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="ee656-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="ee656-111">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="ee656-111">array : 'T[]</span></span>

<span data-ttu-id="ee656-112">Matriz de valores que se van a plegar.</span><span class="sxs-lookup"><span data-stu-id="ee656-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="ee656-113">Salida: ' estado</span><span class="sxs-lookup"><span data-stu-id="ee656-113">Output : 'State</span></span>

<span data-ttu-id="ee656-114">Estado final devuelto por la carpeta después de recorrer en iteración todos los elementos de `array` .</span><span class="sxs-lookup"><span data-stu-id="ee656-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ee656-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ee656-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="ee656-116">' Estado</span><span class="sxs-lookup"><span data-stu-id="ee656-116">'State</span></span>

<span data-ttu-id="ee656-117">El tipo de Estados `folder` en que funciona la función, es decir, acepta como primer argumento y devuelve.</span><span class="sxs-lookup"><span data-stu-id="ee656-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="ee656-118">Traslada</span><span class="sxs-lookup"><span data-stu-id="ee656-118">'T</span></span>

<span data-ttu-id="ee656-119">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="ee656-119">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="ee656-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ee656-120">Example</span></span>

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```