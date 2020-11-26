---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: a6e7519755c4d473f6ba255ac5f877b2a3894d71
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219828"
---
# <a name="zip3-function"></a><span data-ttu-id="f0abe-102">Zip3 (función)</span><span class="sxs-lookup"><span data-stu-id="f0abe-102">Zip3 function</span></span>

<span data-ttu-id="f0abe-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f0abe-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f0abe-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0abe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="f0abe-105">Zip3 (está en desuso.</span><span class="sxs-lookup"><span data-stu-id="f0abe-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="f0abe-106">Use <xref:Microsoft.Quantum.Arrays.Zipped3> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f0abe-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="f0abe-107">Dadas tres matrices, devuelve una nueva matriz de 3 tuplas, de modo que cada una de estas tres tuplas contiene un elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="f0abe-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="f0abe-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f0abe-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="f0abe-109">primero: ' t 1 []</span><span class="sxs-lookup"><span data-stu-id="f0abe-109">first : 'T1[]</span></span>

<span data-ttu-id="f0abe-110">Una matriz que contiene valores para el primer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="f0abe-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="f0abe-111">segundo: ' t 2 []</span><span class="sxs-lookup"><span data-stu-id="f0abe-111">second : 'T2[]</span></span>

<span data-ttu-id="f0abe-112">Una matriz que contiene valores para el segundo elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="f0abe-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="f0abe-113">tercer: ' t 3 []</span><span class="sxs-lookup"><span data-stu-id="f0abe-113">third : 'T3[]</span></span>

<span data-ttu-id="f0abe-114">Una matriz que contiene valores para el tercer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="f0abe-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="f0abe-115">Salida: (' t 1, ' no 2, ' t 3) []</span><span class="sxs-lookup"><span data-stu-id="f0abe-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="f0abe-116">Una matriz que contiene tres tuplas del formulario `(first[idx], second[idx], third[idx])` para cada una de ellas `idx` .</span><span class="sxs-lookup"><span data-stu-id="f0abe-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="f0abe-117">Si las tres matrices no tienen la misma longitud, la salida será tan larga como las entradas más cortas.</span><span class="sxs-lookup"><span data-stu-id="f0abe-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f0abe-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="f0abe-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="f0abe-119">' T 1 '</span><span class="sxs-lookup"><span data-stu-id="f0abe-119">'T1</span></span>

<span data-ttu-id="f0abe-120">Tipo de los primeros elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="f0abe-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="f0abe-121">' T 2</span><span class="sxs-lookup"><span data-stu-id="f0abe-121">'T2</span></span>

<span data-ttu-id="f0abe-122">Tipo de los elementos de la segunda matriz.</span><span class="sxs-lookup"><span data-stu-id="f0abe-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="f0abe-123">No 3</span><span class="sxs-lookup"><span data-stu-id="f0abe-123">'T3</span></span>

<span data-ttu-id="f0abe-124">Tipo de los elementos de la tercera matriz.</span><span class="sxs-lookup"><span data-stu-id="f0abe-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0abe-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0abe-125">See Also</span></span>

- [<span data-ttu-id="f0abe-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="f0abe-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="f0abe-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="f0abe-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)