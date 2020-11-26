---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Descomprimir función
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219964"
---
# <a name="unzipped-function"></a><span data-ttu-id="1482b-102">Descomprimir función</span><span class="sxs-lookup"><span data-stu-id="1482b-102">Unzipped function</span></span>

<span data-ttu-id="1482b-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1482b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1482b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1482b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1482b-105">Dada una matriz de 2-tuplas, devuelve una tupla de dos matrices, cada una con los elementos de las tuplas de la matriz de entrada.</span><span class="sxs-lookup"><span data-stu-id="1482b-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="1482b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1482b-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="1482b-107">ARR: (' t, ' U) []</span><span class="sxs-lookup"><span data-stu-id="1482b-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="1482b-108">Una matriz que contiene dos tuplas</span><span class="sxs-lookup"><span data-stu-id="1482b-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="1482b-109">Salida: (' t [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="1482b-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="1482b-110">Dos matrices, la primera que contiene todos los primeros elementos de las tuplas de entrada, la segunda que contiene todos los segundos elementos de las tuplas de entrada.</span><span class="sxs-lookup"><span data-stu-id="1482b-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1482b-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="1482b-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1482b-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="1482b-112">'T</span></span>

<span data-ttu-id="1482b-113">Tipo del primer elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="1482b-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="1482b-114">' U</span><span class="sxs-lookup"><span data-stu-id="1482b-114">'U</span></span>

<span data-ttu-id="1482b-115">Tipo del segundo elemento de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="1482b-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="1482b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1482b-116">See Also</span></span>

- [<span data-ttu-id="1482b-117">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="1482b-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)