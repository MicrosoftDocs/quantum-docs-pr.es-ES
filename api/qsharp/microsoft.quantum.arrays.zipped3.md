---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: c0535ca4d6e0de13bf809a21e69d100dcb798d1f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729900"
---
# <a name="zipped3-function"></a><span data-ttu-id="b05ae-102">Zipped3 función)</span><span class="sxs-lookup"><span data-stu-id="b05ae-102">Zipped3 function</span></span>

<span data-ttu-id="b05ae-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b05ae-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b05ae-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b05ae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b05ae-105">Dadas tres matrices, devuelve una nueva matriz de 3 tuplas, de modo que cada una de estas tres tuplas contiene un elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="b05ae-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="b05ae-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b05ae-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="b05ae-107">primero: ' t 1 []</span><span class="sxs-lookup"><span data-stu-id="b05ae-107">first : 'T1[]</span></span>

<span data-ttu-id="b05ae-108">Una matriz que contiene valores para el primer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="b05ae-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="b05ae-109">segundo: ' t 2 []</span><span class="sxs-lookup"><span data-stu-id="b05ae-109">second : 'T2[]</span></span>

<span data-ttu-id="b05ae-110">Una matriz que contiene valores para el segundo elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="b05ae-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="b05ae-111">tercer: ' t 3 []</span><span class="sxs-lookup"><span data-stu-id="b05ae-111">third : 'T3[]</span></span>

<span data-ttu-id="b05ae-112">Una matriz que contiene valores para el tercer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="b05ae-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="b05ae-113">Salida: (' t 1, ' no 2, ' t 3) []</span><span class="sxs-lookup"><span data-stu-id="b05ae-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="b05ae-114">Una matriz que contiene tres tuplas del formulario `(first[idx], second[idx], third[idx])` para cada una de ellas `idx` .</span><span class="sxs-lookup"><span data-stu-id="b05ae-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="b05ae-115">Si las tres matrices no tienen la misma longitud, la salida será tan larga como las entradas más cortas.</span><span class="sxs-lookup"><span data-stu-id="b05ae-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b05ae-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="b05ae-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="b05ae-117">' T 1 '</span><span class="sxs-lookup"><span data-stu-id="b05ae-117">'T1</span></span>

<span data-ttu-id="b05ae-118">Tipo de los primeros elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b05ae-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="b05ae-119">' T 2</span><span class="sxs-lookup"><span data-stu-id="b05ae-119">'T2</span></span>

<span data-ttu-id="b05ae-120">Tipo de los elementos de la segunda matriz.</span><span class="sxs-lookup"><span data-stu-id="b05ae-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="b05ae-121">No 3</span><span class="sxs-lookup"><span data-stu-id="b05ae-121">'T3</span></span>

<span data-ttu-id="b05ae-122">Tipo de los elementos de la tercera matriz.</span><span class="sxs-lookup"><span data-stu-id="b05ae-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b05ae-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b05ae-123">See Also</span></span>

- [<span data-ttu-id="b05ae-124">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="b05ae-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="b05ae-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="b05ae-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)