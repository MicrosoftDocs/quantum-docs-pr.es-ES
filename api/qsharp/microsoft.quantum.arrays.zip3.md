---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729917"
---
# <a name="zip3-function"></a><span data-ttu-id="2223d-102">Zip3 (función)</span><span class="sxs-lookup"><span data-stu-id="2223d-102">Zip3 function</span></span>

<span data-ttu-id="2223d-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2223d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2223d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2223d-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="2223d-105">Zip3 (está en desuso.</span><span class="sxs-lookup"><span data-stu-id="2223d-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="2223d-106">Use <xref:Microsoft.Quantum.Arrays.Zipped3> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2223d-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="2223d-107">Dadas tres matrices, devuelve una nueva matriz de 3 tuplas, de modo que cada una de estas tres tuplas contiene un elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="2223d-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="2223d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2223d-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="2223d-109">primero: ' t 1 []</span><span class="sxs-lookup"><span data-stu-id="2223d-109">first : 'T1[]</span></span>

<span data-ttu-id="2223d-110">Una matriz que contiene valores para el primer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="2223d-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="2223d-111">segundo: ' t 2 []</span><span class="sxs-lookup"><span data-stu-id="2223d-111">second : 'T2[]</span></span>

<span data-ttu-id="2223d-112">Una matriz que contiene valores para el segundo elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="2223d-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="2223d-113">tercer: ' t 3 []</span><span class="sxs-lookup"><span data-stu-id="2223d-113">third : 'T3[]</span></span>

<span data-ttu-id="2223d-114">Una matriz que contiene valores para el tercer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="2223d-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="2223d-115">Salida: (' t 1, ' no 2, ' t 3) []</span><span class="sxs-lookup"><span data-stu-id="2223d-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="2223d-116">Una matriz que contiene tres tuplas del formulario `(first[idx], second[idx], third[idx])` para cada una de ellas `idx` .</span><span class="sxs-lookup"><span data-stu-id="2223d-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="2223d-117">Si las tres matrices no tienen la misma longitud, la salida será tan larga como las entradas más cortas.</span><span class="sxs-lookup"><span data-stu-id="2223d-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2223d-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2223d-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="2223d-119">' T 1 '</span><span class="sxs-lookup"><span data-stu-id="2223d-119">'T1</span></span>

<span data-ttu-id="2223d-120">Tipo de los primeros elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="2223d-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="2223d-121">' T 2</span><span class="sxs-lookup"><span data-stu-id="2223d-121">'T2</span></span>

<span data-ttu-id="2223d-122">Tipo de los elementos de la segunda matriz.</span><span class="sxs-lookup"><span data-stu-id="2223d-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="2223d-123">No 3</span><span class="sxs-lookup"><span data-stu-id="2223d-123">'T3</span></span>

<span data-ttu-id="2223d-124">Tipo de los elementos de la tercera matriz.</span><span class="sxs-lookup"><span data-stu-id="2223d-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="2223d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2223d-125">See Also</span></span>

- [<span data-ttu-id="2223d-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="2223d-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="2223d-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="2223d-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)