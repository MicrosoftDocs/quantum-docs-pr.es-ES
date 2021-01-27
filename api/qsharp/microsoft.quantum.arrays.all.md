---
uid: Microsoft.Quantum.Arrays.All
title: All (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842897"
---
# <a name="all-function"></a><span data-ttu-id="fcb6c-102">All (función)</span><span class="sxs-lookup"><span data-stu-id="fcb6c-102">All function</span></span>

<span data-ttu-id="fcb6c-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fcb6c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fcb6c-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fcb6c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fcb6c-105">Dada una matriz y un predicado definidos para los elementos de la matriz, y comprueba si todos los elementos de la matriz satisfacen el predicado.</span><span class="sxs-lookup"><span data-stu-id="fcb6c-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="fcb6c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fcb6c-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="fcb6c-107">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fcb6c-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fcb6c-108">Función de `'T` a `Bool` que se usa para comprobar los elementos.</span><span class="sxs-lookup"><span data-stu-id="fcb6c-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="fcb6c-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="fcb6c-109">array : 'T[]</span></span>

<span data-ttu-id="fcb6c-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="fcb6c-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fcb6c-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fcb6c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fcb6c-112">Un `Bool` valor de la función y del predicado que se aplica a todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="fcb6c-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fcb6c-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="fcb6c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fcb6c-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="fcb6c-114">'T</span></span>

<span data-ttu-id="fcb6c-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="fcb6c-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="fcb6c-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fcb6c-116">Example</span></span>

<span data-ttu-id="fcb6c-117">El código siguiente comprueba si todos los elementos de la matriz son distintos de cero:</span><span class="sxs-lookup"><span data-stu-id="fcb6c-117">The following code checks whether all elements of the array are non-zero:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a><span data-ttu-id="fcb6c-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fcb6c-118">Remarks</span></span>

<span data-ttu-id="fcb6c-119">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una función `predicate: 'T -> Bool` podemos generar un `Bool` valor que indica si todos los elementos cumplen `predicate` .</span><span class="sxs-lookup"><span data-stu-id="fcb6c-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>