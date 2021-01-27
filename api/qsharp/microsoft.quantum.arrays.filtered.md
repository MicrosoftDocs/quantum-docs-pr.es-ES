---
uid: Microsoft.Quantum.Arrays.Filtered
title: Función filtrada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847163"
---
# <a name="filtered-function"></a><span data-ttu-id="35485-102">Función filtrada</span><span class="sxs-lookup"><span data-stu-id="35485-102">Filtered function</span></span>

<span data-ttu-id="35485-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="35485-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="35485-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35485-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35485-105">Dada una matriz y un predicado definidos para los elementos de la matriz, devuelve una matriz que consta de los elementos que cumplen el predicado.</span><span class="sxs-lookup"><span data-stu-id="35485-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="35485-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="35485-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="35485-107">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="35485-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="35485-108">Función de `'T` a un valor booleano que se usa para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="35485-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="35485-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="35485-109">array : 'T[]</span></span>

<span data-ttu-id="35485-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="35485-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="35485-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="35485-111">Output : 'T[]</span></span>

<span data-ttu-id="35485-112">Matriz `'T[]` de elementos que satisfacen el predicado.</span><span class="sxs-lookup"><span data-stu-id="35485-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="35485-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="35485-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35485-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="35485-114">'T</span></span>

<span data-ttu-id="35485-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="35485-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="35485-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35485-116">Example</span></span>

<span data-ttu-id="35485-117">En el código siguiente se muestra la función "Filtered".</span><span class="sxs-lookup"><span data-stu-id="35485-117">The following code demonstrates the "Filtered" function.</span></span>
<span data-ttu-id="35485-118">Un predicado se define mediante la @"microsoft.quantum.logical.greaterthani" función:</span><span class="sxs-lookup"><span data-stu-id="35485-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

<span data-ttu-id="35485-119">El resultado que debería esperar de este ejemplo será una matriz de números mayor que 5.</span><span class="sxs-lookup"><span data-stu-id="35485-119">The outcome one should expect from this example will be an array of numbers greater than 5.</span></span>

## <a name="remarks"></a><span data-ttu-id="35485-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35485-120">Remarks</span></span>

<span data-ttu-id="35485-121">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y un predicado, `'T -> Bool` podemos filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="35485-121">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>