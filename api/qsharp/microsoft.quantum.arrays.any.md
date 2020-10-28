---
uid: Microsoft.Quantum.Arrays.Any
title: Cualquier función
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: dd5639f1b0a76cb356c89aca0c0e02d375f30d12
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730420"
---
# <a name="any-function"></a><span data-ttu-id="b3fdb-102">Cualquier función</span><span class="sxs-lookup"><span data-stu-id="b3fdb-102">Any function</span></span>

<span data-ttu-id="b3fdb-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b3fdb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b3fdb-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3fdb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3fdb-105">Dada una matriz y un predicado definidos para los elementos de la matriz, comprueba si al menos un elemento de la matriz satisface el predicado.</span><span class="sxs-lookup"><span data-stu-id="b3fdb-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="b3fdb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b3fdb-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="b3fdb-107">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b3fdb-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b3fdb-108">Función de `'T` a `Bool` que se usa para comprobar los elementos.</span><span class="sxs-lookup"><span data-stu-id="b3fdb-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="b3fdb-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="b3fdb-109">array : 'T[]</span></span>

<span data-ttu-id="b3fdb-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="b3fdb-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b3fdb-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b3fdb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b3fdb-112">Un `Bool` valor de la función o del predicado que se aplica a todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="b3fdb-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b3fdb-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="b3fdb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b3fdb-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="b3fdb-114">'T</span></span>

<span data-ttu-id="b3fdb-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="b3fdb-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="b3fdb-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b3fdb-116">Remarks</span></span>

<span data-ttu-id="b3fdb-117">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una función, `predicate: 'T -> Bool` podemos generar un `Bool` valor que indica si algún elemento satisface `predicate` .</span><span class="sxs-lookup"><span data-stu-id="b3fdb-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>