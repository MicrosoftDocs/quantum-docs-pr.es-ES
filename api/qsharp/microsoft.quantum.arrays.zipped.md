---
uid: Microsoft.Quantum.Arrays.Zipped
title: Función Zip
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729909"
---
# <a name="zipped-function"></a><span data-ttu-id="ae2b5-102">Función Zip</span><span class="sxs-lookup"><span data-stu-id="ae2b5-102">Zipped function</span></span>

<span data-ttu-id="ae2b5-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ae2b5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ae2b5-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae2b5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae2b5-105">Dadas dos matrices, devuelve una nueva matriz de pares de modo que cada par contiene un elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="ae2b5-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="ae2b5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ae2b5-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="ae2b5-107">Left: ' t []</span><span class="sxs-lookup"><span data-stu-id="ae2b5-107">left : 'T[]</span></span>

<span data-ttu-id="ae2b5-108">Una matriz que contiene valores para el primer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="ae2b5-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="ae2b5-109">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="ae2b5-109">right : 'U[]</span></span>

<span data-ttu-id="ae2b5-110">Una matriz que contiene valores para el segundo elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="ae2b5-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="ae2b5-111">Salida: (' t, ' U) []</span><span class="sxs-lookup"><span data-stu-id="ae2b5-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="ae2b5-112">Una matriz que contiene pares del formulario `(left[idx], right[idx])` para cada `idx` .</span><span class="sxs-lookup"><span data-stu-id="ae2b5-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="ae2b5-113">Si las dos matrices no tienen la misma longitud, la salida será tan larga como las entradas más cortas.</span><span class="sxs-lookup"><span data-stu-id="ae2b5-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ae2b5-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ae2b5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ae2b5-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="ae2b5-115">'T</span></span>

<span data-ttu-id="ae2b5-116">Tipo de los elementos de la matriz izquierda.</span><span class="sxs-lookup"><span data-stu-id="ae2b5-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="ae2b5-117">' U</span><span class="sxs-lookup"><span data-stu-id="ae2b5-117">'U</span></span>

<span data-ttu-id="ae2b5-118">Tipo de los elementos de la matriz de la derecha.</span><span class="sxs-lookup"><span data-stu-id="ae2b5-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae2b5-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae2b5-119">See Also</span></span>

- [<span data-ttu-id="ae2b5-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="ae2b5-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="ae2b5-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="ae2b5-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="ae2b5-122">Microsoft. Quantum. matrices. descomprimido</span><span class="sxs-lookup"><span data-stu-id="ae2b5-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)