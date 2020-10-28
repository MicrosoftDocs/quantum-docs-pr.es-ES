---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d42b3b6db059163f6c766d4f133551be293c153d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729901"
---
# <a name="zip4-function"></a><span data-ttu-id="809a4-102">Zip4 función)</span><span class="sxs-lookup"><span data-stu-id="809a4-102">Zip4 function</span></span>

<span data-ttu-id="809a4-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="809a4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="809a4-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="809a4-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="809a4-105">Zip4 está en desuso.</span><span class="sxs-lookup"><span data-stu-id="809a4-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="809a4-106">Use <xref:Microsoft.Quantum.Arrays.Zipped4> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="809a4-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="809a4-107">Dadas cuatro matrices, devuelve una nueva matriz de 4 tuplas, de modo que cada tupla de 4 contiene un elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="809a4-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="809a4-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="809a4-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="809a4-109">primero: ' t 1 []</span><span class="sxs-lookup"><span data-stu-id="809a4-109">first : 'T1[]</span></span>

<span data-ttu-id="809a4-110">Una matriz que contiene valores para el primer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="809a4-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="809a4-111">segundo: ' t 2 []</span><span class="sxs-lookup"><span data-stu-id="809a4-111">second : 'T2[]</span></span>

<span data-ttu-id="809a4-112">Una matriz que contiene valores para el segundo elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="809a4-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="809a4-113">tercer: ' t 3 []</span><span class="sxs-lookup"><span data-stu-id="809a4-113">third : 'T3[]</span></span>

<span data-ttu-id="809a4-114">Una matriz que contiene valores para el tercer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="809a4-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="809a4-115">cuarto: ' t 4 []</span><span class="sxs-lookup"><span data-stu-id="809a4-115">fourth : 'T4[]</span></span>

<span data-ttu-id="809a4-116">Una matriz que contiene valores para el cuarto elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="809a4-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="809a4-117">Salida: (' t 1, ' no 2, ' t 3, ' t 4 ') []</span><span class="sxs-lookup"><span data-stu-id="809a4-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="809a4-118">Una matriz que contiene cuatro tuplas del formulario `(first[idx], second[idx], third[idx], fourth[idx])` para cada una de ellas `idx` .</span><span class="sxs-lookup"><span data-stu-id="809a4-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="809a4-119">Si las cuatro matrices no tienen la misma longitud, la salida será tan larga como las entradas más cortas.</span><span class="sxs-lookup"><span data-stu-id="809a4-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="809a4-120">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="809a4-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="809a4-121">' T 1 '</span><span class="sxs-lookup"><span data-stu-id="809a4-121">'T1</span></span>

<span data-ttu-id="809a4-122">Tipo de los primeros elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="809a4-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="809a4-123">' T 2</span><span class="sxs-lookup"><span data-stu-id="809a4-123">'T2</span></span>

<span data-ttu-id="809a4-124">Tipo de los elementos de la segunda matriz.</span><span class="sxs-lookup"><span data-stu-id="809a4-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="809a4-125">No 3</span><span class="sxs-lookup"><span data-stu-id="809a4-125">'T3</span></span>

<span data-ttu-id="809a4-126">Tipo de los elementos de la tercera matriz.</span><span class="sxs-lookup"><span data-stu-id="809a4-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="809a4-127">No 4</span><span class="sxs-lookup"><span data-stu-id="809a4-127">'T4</span></span>

<span data-ttu-id="809a4-128">El tipo de los cuatro elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="809a4-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="809a4-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="809a4-129">See Also</span></span>

- [<span data-ttu-id="809a4-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="809a4-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="809a4-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="809a4-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)