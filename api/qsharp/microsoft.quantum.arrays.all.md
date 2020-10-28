---
uid: Microsoft.Quantum.Arrays.All
title: All (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730421"
---
# <a name="all-function"></a><span data-ttu-id="63875-102">All (función)</span><span class="sxs-lookup"><span data-stu-id="63875-102">All function</span></span>

<span data-ttu-id="63875-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="63875-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="63875-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63875-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63875-105">Dada una matriz y un predicado definidos para los elementos de la matriz, y comprueba si todos los elementos de la matriz satisfacen el predicado.</span><span class="sxs-lookup"><span data-stu-id="63875-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="63875-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="63875-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="63875-107">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="63875-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63875-108">Función de `'T` a `Bool` que se usa para comprobar los elementos.</span><span class="sxs-lookup"><span data-stu-id="63875-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="63875-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="63875-109">array : 'T[]</span></span>

<span data-ttu-id="63875-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="63875-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="63875-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="63875-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63875-112">Un `Bool` valor de la función y del predicado que se aplica a todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="63875-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="63875-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="63875-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63875-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="63875-114">'T</span></span>

<span data-ttu-id="63875-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="63875-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="63875-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="63875-116">Remarks</span></span>

<span data-ttu-id="63875-117">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una función `predicate: 'T -> Bool` podemos generar un `Bool` valor que indica si todos los elementos cumplen `predicate` .</span><span class="sxs-lookup"><span data-stu-id="63875-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>