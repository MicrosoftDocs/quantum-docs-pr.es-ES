---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: b2c5f11c0d92ddf9214de2d439c175319c569be0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220843"
---
# <a name="issorted-function"></a><span data-ttu-id="538b3-102">IsSorted (función)</span><span class="sxs-lookup"><span data-stu-id="538b3-102">IsSorted function</span></span>

<span data-ttu-id="538b3-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="538b3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="538b3-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="538b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="538b3-105">Dada una matriz, devuelve si esa matriz se ordena según lo definido por una función de comparación determinada.</span><span class="sxs-lookup"><span data-stu-id="538b3-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="538b3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="538b3-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="538b3-107">comparación: (' t, ')-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="538b3-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="538b3-108">Función que compara dos elementos que `a` se considera que son menores o iguales que `b` si `comparison(a, b)` es `true` .</span><span class="sxs-lookup"><span data-stu-id="538b3-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="538b3-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="538b3-109">array : 'T[]</span></span>

<span data-ttu-id="538b3-110">Matriz que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="538b3-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="538b3-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="538b3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="538b3-112">`true` Si y solo si para cada par de elementos `a` y `b` `array` se producen en ese orden, `comparison(a, b)` es `true` .</span><span class="sxs-lookup"><span data-stu-id="538b3-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="538b3-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="538b3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="538b3-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="538b3-114">'T</span></span>

<span data-ttu-id="538b3-115">Tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="538b3-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="538b3-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="538b3-116">Remarks</span></span>

<span data-ttu-id="538b3-117">Se supone que la función `comparison` es transitiva, de modo que si `comparison(a, b)` y `comparison(b, c)` , `comparison(a, c)` se supone.</span><span class="sxs-lookup"><span data-stu-id="538b3-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="538b3-118">Si esta propiedad no contiene, la salida de esta función puede ser incorrecta.</span><span class="sxs-lookup"><span data-stu-id="538b3-118">If this property does not hold, then the output of this function may be incorrect.</span></span>