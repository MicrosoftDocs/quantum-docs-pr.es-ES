---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 6a4ffaeff8e6248a708ab9f8f9a6ff0c2e9e08d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842187"
---
# <a name="zipped3-function"></a><span data-ttu-id="dda1e-102">Zipped3 función)</span><span class="sxs-lookup"><span data-stu-id="dda1e-102">Zipped3 function</span></span>

<span data-ttu-id="dda1e-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dda1e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dda1e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dda1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dda1e-105">Dadas tres matrices, devuelve una nueva matriz de 3 tuplas, de modo que cada una de estas tres tuplas contiene un elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="dda1e-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="dda1e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dda1e-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="dda1e-107">primero: ' t 1 []</span><span class="sxs-lookup"><span data-stu-id="dda1e-107">first : 'T1[]</span></span>

<span data-ttu-id="dda1e-108">Una matriz que contiene valores para el primer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="dda1e-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="dda1e-109">segundo: ' t 2 []</span><span class="sxs-lookup"><span data-stu-id="dda1e-109">second : 'T2[]</span></span>

<span data-ttu-id="dda1e-110">Una matriz que contiene valores para el segundo elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="dda1e-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="dda1e-111">tercer: ' t 3 []</span><span class="sxs-lookup"><span data-stu-id="dda1e-111">third : 'T3[]</span></span>

<span data-ttu-id="dda1e-112">Una matriz que contiene valores para el tercer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="dda1e-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="dda1e-113">Salida: (' t 1, ' no 2, ' t 3) []</span><span class="sxs-lookup"><span data-stu-id="dda1e-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="dda1e-114">Una matriz que contiene tres tuplas del formulario `(first[idx], second[idx], third[idx])` para cada una de ellas `idx` .</span><span class="sxs-lookup"><span data-stu-id="dda1e-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="dda1e-115">Si las tres matrices no tienen la misma longitud, la salida será tan larga como las entradas más cortas.</span><span class="sxs-lookup"><span data-stu-id="dda1e-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dda1e-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="dda1e-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="dda1e-117">' T 1 '</span><span class="sxs-lookup"><span data-stu-id="dda1e-117">'T1</span></span>

<span data-ttu-id="dda1e-118">Tipo de los primeros elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="dda1e-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="dda1e-119">' T 2</span><span class="sxs-lookup"><span data-stu-id="dda1e-119">'T2</span></span>

<span data-ttu-id="dda1e-120">Tipo de los elementos de la segunda matriz.</span><span class="sxs-lookup"><span data-stu-id="dda1e-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="dda1e-121">No 3</span><span class="sxs-lookup"><span data-stu-id="dda1e-121">'T3</span></span>

<span data-ttu-id="dda1e-122">Tipo de los elementos de la tercera matriz.</span><span class="sxs-lookup"><span data-stu-id="dda1e-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="dda1e-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dda1e-123">See Also</span></span>

- [<span data-ttu-id="dda1e-124">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="dda1e-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="dda1e-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="dda1e-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)