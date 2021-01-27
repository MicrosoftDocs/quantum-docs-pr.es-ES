---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 8ed658003f749efd31b8d841cecbb0a23a471af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850897"
---
# <a name="zip-function"></a><span data-ttu-id="630b8-102">Zip (función)</span><span class="sxs-lookup"><span data-stu-id="630b8-102">Zip function</span></span>

<span data-ttu-id="630b8-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="630b8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="630b8-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="630b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="630b8-105">Zip está en desuso.</span><span class="sxs-lookup"><span data-stu-id="630b8-105">Zip has been deprecated.</span></span> <span data-ttu-id="630b8-106">Use <xref:Microsoft.Quantum.Arrays.Zipped> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="630b8-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="630b8-107">Dadas dos matrices, devuelve una nueva matriz de pares de modo que cada par contiene un elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="630b8-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="630b8-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="630b8-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="630b8-109">Left: ' t []</span><span class="sxs-lookup"><span data-stu-id="630b8-109">left : 'T[]</span></span>

<span data-ttu-id="630b8-110">Una matriz que contiene valores para el primer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="630b8-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="630b8-111">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="630b8-111">right : 'U[]</span></span>

<span data-ttu-id="630b8-112">Una matriz que contiene valores para el segundo elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="630b8-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="630b8-113">Salida: (' t, ' U) []</span><span class="sxs-lookup"><span data-stu-id="630b8-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="630b8-114">Una matriz que contiene pares del formulario `(left[idx], right[idx])` para cada `idx` .</span><span class="sxs-lookup"><span data-stu-id="630b8-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="630b8-115">Si las dos matrices no tienen la misma longitud, la salida será tan larga como las entradas más cortas.</span><span class="sxs-lookup"><span data-stu-id="630b8-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="630b8-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="630b8-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="630b8-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="630b8-117">'T</span></span>

<span data-ttu-id="630b8-118">Tipo de los elementos de la matriz izquierda.</span><span class="sxs-lookup"><span data-stu-id="630b8-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="630b8-119">' U</span><span class="sxs-lookup"><span data-stu-id="630b8-119">'U</span></span>

<span data-ttu-id="630b8-120">Tipo de los elementos de la matriz de la derecha.</span><span class="sxs-lookup"><span data-stu-id="630b8-120">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="630b8-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="630b8-121">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zip(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="630b8-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="630b8-122">See Also</span></span>

- [<span data-ttu-id="630b8-123">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="630b8-123">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="630b8-124">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="630b8-124">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="630b8-125">Microsoft. Quantum. matrices. descomprimido</span><span class="sxs-lookup"><span data-stu-id="630b8-125">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)