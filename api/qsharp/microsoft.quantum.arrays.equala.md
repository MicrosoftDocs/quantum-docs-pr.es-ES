---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equala (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730293"
---
# <a name="equala-function"></a><span data-ttu-id="bbd17-102">Equala (función)</span><span class="sxs-lookup"><span data-stu-id="bbd17-102">EqualA function</span></span>

<span data-ttu-id="bbd17-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bbd17-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bbd17-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bbd17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bbd17-105">Dadas dos matrices del mismo tipo y un predicado definido para pares de elementos de las matrices, comprueba si las matrices son iguales.</span><span class="sxs-lookup"><span data-stu-id="bbd17-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="bbd17-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bbd17-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="bbd17-107">igual: (' t, ')-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bbd17-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bbd17-108">Función de Tuple `('T, 'T)` a `Bool` que se usa para comprobar si dos elementos de matrices son iguales.</span><span class="sxs-lookup"><span data-stu-id="bbd17-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="bbd17-109">matriz1: ' t []</span><span class="sxs-lookup"><span data-stu-id="bbd17-109">array1 : 'T[]</span></span>

<span data-ttu-id="bbd17-110">Primera matriz que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="bbd17-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="bbd17-111">matriz2: ' t []</span><span class="sxs-lookup"><span data-stu-id="bbd17-111">array2 : 'T[]</span></span>

<span data-ttu-id="bbd17-112">Segunda matriz que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="bbd17-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bbd17-113">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bbd17-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bbd17-114">Valor `true` si y solo si `array1` y `array2` son iguales.</span><span class="sxs-lookup"><span data-stu-id="bbd17-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="bbd17-115">Es decir, si ambas matrices tienen la misma longitud y todos los elementos son iguales que los definidos por `equal` .</span><span class="sxs-lookup"><span data-stu-id="bbd17-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bbd17-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="bbd17-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bbd17-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="bbd17-117">'T</span></span>

<span data-ttu-id="bbd17-118">Tipo de los elementos de cada matriz.</span><span class="sxs-lookup"><span data-stu-id="bbd17-118">The type of each array's elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="bbd17-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bbd17-119">Remarks</span></span>

<span data-ttu-id="bbd17-120">Esta función se define para tipos genéricos; es decir, cada vez que tenemos dos matrices `'T[]` y una función `equal: ('T, 'T) -> Bool` , esta función devuelve un `Bool` valor que indica si las matrices son iguales.</span><span class="sxs-lookup"><span data-stu-id="bbd17-120">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="bbd17-121">Para que dos matrices se consideren iguales, deben tener la misma longitud y los elementos de las mismas posiciones en las matrices deben ser iguales.</span><span class="sxs-lookup"><span data-stu-id="bbd17-121">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>