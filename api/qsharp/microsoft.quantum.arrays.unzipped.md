---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Descomprimir función
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845380"
---
# <a name="unzipped-function"></a><span data-ttu-id="e5834-102">Descomprimir función</span><span class="sxs-lookup"><span data-stu-id="e5834-102">Unzipped function</span></span>

<span data-ttu-id="e5834-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e5834-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e5834-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5834-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5834-105">Dada una matriz de 2-tuplas, devuelve una tupla de dos matrices, cada una con los elementos de las tuplas de la matriz de entrada.</span><span class="sxs-lookup"><span data-stu-id="e5834-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="e5834-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e5834-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="e5834-107">ARR: (' t, ' U) []</span><span class="sxs-lookup"><span data-stu-id="e5834-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="e5834-108">Una matriz que contiene dos tuplas</span><span class="sxs-lookup"><span data-stu-id="e5834-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="e5834-109">Salida: (' t [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="e5834-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="e5834-110">Dos matrices, la primera que contiene todos los primeros elementos de las tuplas de entrada, la segunda que contiene todos los segundos elementos de las tuplas de entrada.</span><span class="sxs-lookup"><span data-stu-id="e5834-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e5834-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="e5834-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e5834-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="e5834-112">'T</span></span>

<span data-ttu-id="e5834-113">Tipo del primer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="e5834-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="e5834-114">' U</span><span class="sxs-lookup"><span data-stu-id="e5834-114">'U</span></span>

<span data-ttu-id="e5834-115">Tipo del segundo elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="e5834-115">The type of the second element in each tuple</span></span>

## <a name="example"></a><span data-ttu-id="e5834-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5834-116">Example</span></span>

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a><span data-ttu-id="e5834-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5834-117">See Also</span></span>

- [<span data-ttu-id="e5834-118">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="e5834-118">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)