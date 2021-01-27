---
uid: Microsoft.Quantum.Arrays.Unique
title: Función Unique
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850925"
---
# <a name="unique-function"></a><span data-ttu-id="2866e-102">Función Unique</span><span class="sxs-lookup"><span data-stu-id="2866e-102">Unique function</span></span>

<span data-ttu-id="2866e-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2866e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2866e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2866e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2866e-105">Devuelve una nueva matriz que no tiene elementos adyacentes iguales.</span><span class="sxs-lookup"><span data-stu-id="2866e-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="2866e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2866e-106">Description</span></span>

<span data-ttu-id="2866e-107">Dada una matriz de elementos y una función para probar la igualdad, esta función devuelve una nueva matriz en la que se conserva el orden relativo de los elementos, pero todos los elementos adyacentes que son iguales se filtran por un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="2866e-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="2866e-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2866e-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="2866e-109">igual: (' t, ')-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2866e-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2866e-110">Función que compara dos elementos que `a` se considera que son iguales que `b` si `equal(a, b)` es `true` .</span><span class="sxs-lookup"><span data-stu-id="2866e-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="2866e-111">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="2866e-111">array : 'T[]</span></span>

<span data-ttu-id="2866e-112">Matriz que se va a filtrar para los elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="2866e-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="2866e-113">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="2866e-113">Output : 'T[]</span></span>

<span data-ttu-id="2866e-114">Matriz sin elementos adyacentes iguales.</span><span class="sxs-lookup"><span data-stu-id="2866e-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2866e-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2866e-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2866e-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="2866e-116">'T</span></span>

<span data-ttu-id="2866e-117">Tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="2866e-117">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="2866e-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2866e-118">Example</span></span>

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a><span data-ttu-id="2866e-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2866e-119">Remarks</span></span>

<span data-ttu-id="2866e-120">Si hay varios elementos que son iguales pero no próximos entre sí, habrá varias repeticiones en la matriz de salida.</span><span class="sxs-lookup"><span data-stu-id="2866e-120">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="2866e-121">Use esta función junto con `Sorted` para obtener una matriz con elementos únicos generales.</span><span class="sxs-lookup"><span data-stu-id="2866e-121">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>