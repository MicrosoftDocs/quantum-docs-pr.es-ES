---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operación ForEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730237"
---
# <a name="foreach-operation"></a><span data-ttu-id="f3a52-102">Operación ForEach</span><span class="sxs-lookup"><span data-stu-id="f3a52-102">ForEach operation</span></span>

<span data-ttu-id="f3a52-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f3a52-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f3a52-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3a52-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3a52-105">Dada una matriz y una operación que se define para los elementos de la matriz, devuelve una nueva matriz que consta de las imágenes de la matriz original en la operación.</span><span class="sxs-lookup"><span data-stu-id="f3a52-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="f3a52-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f3a52-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="f3a52-107">acción: ' t => ' U</span><span class="sxs-lookup"><span data-stu-id="f3a52-107">action : 'T => 'U</span></span> 

<span data-ttu-id="f3a52-108">Una operación de `'T` a `'U` que se aplica a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="f3a52-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="f3a52-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="f3a52-109">array : 'T[]</span></span>

<span data-ttu-id="f3a52-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="f3a52-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="f3a52-111">Salida: ' U []</span><span class="sxs-lookup"><span data-stu-id="f3a52-111">Output : 'U[]</span></span>

<span data-ttu-id="f3a52-112">Matriz `'U[]` de elementos que se asignan mediante la `action` operación.</span><span class="sxs-lookup"><span data-stu-id="f3a52-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f3a52-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="f3a52-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f3a52-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="f3a52-114">'T</span></span>

<span data-ttu-id="f3a52-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="f3a52-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="f3a52-116">' U</span><span class="sxs-lookup"><span data-stu-id="f3a52-116">'U</span></span>

<span data-ttu-id="f3a52-117">El tipo de resultado de la `action` operación.</span><span class="sxs-lookup"><span data-stu-id="f3a52-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="f3a52-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f3a52-118">Remarks</span></span>

<span data-ttu-id="f3a52-119">La operación se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una operación, `action : 'T -> 'U` podemos asignar los elementos de la matriz y generar una nueva matriz de tipo `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="f3a52-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>