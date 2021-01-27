---
uid: Microsoft.Quantum.Arrays.Count
title: Count, función
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842849"
---
# <a name="count-function"></a><span data-ttu-id="1e68f-102">Count, función</span><span class="sxs-lookup"><span data-stu-id="1e68f-102">Count function</span></span>

<span data-ttu-id="1e68f-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1e68f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1e68f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e68f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e68f-105">Dada una matriz y un predicado definidos para los elementos de la matriz, devuelve el número de elementos de una matriz que consta de los elementos que cumplen el predicado.</span><span class="sxs-lookup"><span data-stu-id="1e68f-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="1e68f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1e68f-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="1e68f-107">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1e68f-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1e68f-108">Función de `'T` a un valor booleano que se usa para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="1e68f-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="1e68f-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="1e68f-109">array : 'T[]</span></span>

<span data-ttu-id="1e68f-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="1e68f-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="1e68f-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1e68f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1e68f-112">Número de elementos de `array` que satisfacen el predicado.</span><span class="sxs-lookup"><span data-stu-id="1e68f-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1e68f-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="1e68f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1e68f-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="1e68f-114">'T</span></span>

<span data-ttu-id="1e68f-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="1e68f-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="1e68f-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1e68f-116">Example</span></span>

<span data-ttu-id="1e68f-117">En el código siguiente se muestra la función "Count".</span><span class="sxs-lookup"><span data-stu-id="1e68f-117">The following code demonstrates the "Count" function.</span></span>
<span data-ttu-id="1e68f-118">Un predicado se define mediante la @"microsoft.quantum.logical.greaterthani" función:</span><span class="sxs-lookup"><span data-stu-id="1e68f-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a><span data-ttu-id="1e68f-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1e68f-119">Remarks</span></span>

<span data-ttu-id="1e68f-120">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y un predicado, `'T -> Bool` podemos filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="1e68f-120">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>