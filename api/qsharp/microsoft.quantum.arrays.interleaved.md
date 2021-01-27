---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Función intercalada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848115"
---
# <a name="interleaved-function"></a><span data-ttu-id="4d600-102">Función intercalada</span><span class="sxs-lookup"><span data-stu-id="4d600-102">Interleaved function</span></span>

<span data-ttu-id="4d600-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4d600-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4d600-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d600-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d600-105">Intercala dos matrices de (casi) el mismo tamaño.</span><span class="sxs-lookup"><span data-stu-id="4d600-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="4d600-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d600-106">Description</span></span>

<span data-ttu-id="4d600-107">Esta función devuelve el intercalado de dos matrices, comenzando por el primer elemento de la primera matriz, el primer elemento de la segunda matriz, etc.</span><span class="sxs-lookup"><span data-stu-id="4d600-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="4d600-108">La primera matriz debe tener la misma longitud que la segunda, o bien puede tener un elemento más.</span><span class="sxs-lookup"><span data-stu-id="4d600-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="4d600-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="4d600-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="4d600-110">primero: ' t []</span><span class="sxs-lookup"><span data-stu-id="4d600-110">first : 'T[]</span></span>

<span data-ttu-id="4d600-111">Primera matriz que se va a intercalar.</span><span class="sxs-lookup"><span data-stu-id="4d600-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="4d600-112">segundo: ' t []</span><span class="sxs-lookup"><span data-stu-id="4d600-112">second : 'T[]</span></span>

<span data-ttu-id="4d600-113">Segunda matriz que se va a intercalar.</span><span class="sxs-lookup"><span data-stu-id="4d600-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="4d600-114">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="4d600-114">Output : 'T[]</span></span>

<span data-ttu-id="4d600-115">Matriz intercalada</span><span class="sxs-lookup"><span data-stu-id="4d600-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4d600-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="4d600-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4d600-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="4d600-117">'T</span></span>

<span data-ttu-id="4d600-118">Tipo de cada elemento de `first` y `second` .</span><span class="sxs-lookup"><span data-stu-id="4d600-118">The type of each element of `first` and `second`.</span></span>

## <a name="example"></a><span data-ttu-id="4d600-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d600-119">Example</span></span>

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```