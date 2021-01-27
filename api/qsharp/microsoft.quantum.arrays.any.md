---
uid: Microsoft.Quantum.Arrays.Any
title: Cualquier función
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: a05f9531168bf2b32977665d38cc00f3c8e64879
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846278"
---
# <a name="any-function"></a><span data-ttu-id="406d8-102">Cualquier función</span><span class="sxs-lookup"><span data-stu-id="406d8-102">Any function</span></span>

<span data-ttu-id="406d8-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="406d8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="406d8-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="406d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="406d8-105">Dada una matriz y un predicado definidos para los elementos de la matriz, comprueba si al menos un elemento de la matriz satisface el predicado.</span><span class="sxs-lookup"><span data-stu-id="406d8-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="406d8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="406d8-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="406d8-107">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="406d8-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="406d8-108">Función de `'T` a `Bool` que se usa para comprobar los elementos.</span><span class="sxs-lookup"><span data-stu-id="406d8-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="406d8-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="406d8-109">array : 'T[]</span></span>

<span data-ttu-id="406d8-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="406d8-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="406d8-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="406d8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="406d8-112">Un `Bool` valor de la función o del predicado que se aplica a todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="406d8-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="406d8-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="406d8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="406d8-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="406d8-114">'T</span></span>

<span data-ttu-id="406d8-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="406d8-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="406d8-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="406d8-116">Example</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function IsThreePresent() : Bool {
    let arrayOfInts = [1, 2, 3, 4, 5];
    let is3Present = IsNumberPresentInArray(3, arrayOfInts);
    return is3Present;
}

function IsNumberPresentInArray(n : Int, array : Int[]) : Bool {
    return Any(EqualI(_, n), array);
}
```

## <a name="remarks"></a><span data-ttu-id="406d8-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="406d8-117">Remarks</span></span>

<span data-ttu-id="406d8-118">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una función, `predicate: 'T -> Bool` podemos generar un `Bool` valor que indica si algún elemento satisface `predicate` .</span><span class="sxs-lookup"><span data-stu-id="406d8-118">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>