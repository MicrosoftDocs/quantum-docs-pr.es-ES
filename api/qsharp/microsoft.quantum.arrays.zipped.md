---
uid: Microsoft.Quantum.Arrays.Zipped
title: Función Zip
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219760"
---
# <a name="zipped-function"></a><span data-ttu-id="adda7-102">Función Zip</span><span class="sxs-lookup"><span data-stu-id="adda7-102">Zipped function</span></span>

<span data-ttu-id="adda7-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="adda7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="adda7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="adda7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="adda7-105">Dadas dos matrices, devuelve una nueva matriz de pares de modo que cada par contiene un elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="adda7-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="adda7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="adda7-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="adda7-107">Left: ' t []</span><span class="sxs-lookup"><span data-stu-id="adda7-107">left : 'T[]</span></span>

<span data-ttu-id="adda7-108">Una matriz que contiene valores para el primer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="adda7-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="adda7-109">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="adda7-109">right : 'U[]</span></span>

<span data-ttu-id="adda7-110">Una matriz que contiene valores para el segundo elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="adda7-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="adda7-111">Salida: (' t, ' U) []</span><span class="sxs-lookup"><span data-stu-id="adda7-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="adda7-112">Una matriz que contiene pares del formulario `(left[idx], right[idx])` para cada `idx` .</span><span class="sxs-lookup"><span data-stu-id="adda7-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="adda7-113">Si las dos matrices no tienen la misma longitud, la salida será tan larga como las entradas más cortas.</span><span class="sxs-lookup"><span data-stu-id="adda7-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="adda7-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="adda7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="adda7-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="adda7-115">'T</span></span>

<span data-ttu-id="adda7-116">Tipo de los elementos de la matriz izquierda.</span><span class="sxs-lookup"><span data-stu-id="adda7-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="adda7-117">' U</span><span class="sxs-lookup"><span data-stu-id="adda7-117">'U</span></span>

<span data-ttu-id="adda7-118">Tipo de los elementos de la matriz de la derecha.</span><span class="sxs-lookup"><span data-stu-id="adda7-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="adda7-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="adda7-119">See Also</span></span>

- [<span data-ttu-id="adda7-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="adda7-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="adda7-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="adda7-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="adda7-122">Microsoft. Quantum. matrices. descomprimido</span><span class="sxs-lookup"><span data-stu-id="adda7-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)