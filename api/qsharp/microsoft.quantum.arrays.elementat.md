---
uid: Microsoft.Quantum.Arrays.ElementAt
title: ElementAt función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementAt
qsharp.summary: Returns the at the given index of an array.
ms.openlocfilehash: 2d31c62a4a5ba3b273e7440b5dfe4482b47e3a8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842815"
---
# <a name="elementat-function"></a><span data-ttu-id="8b108-102">ElementAt función)</span><span class="sxs-lookup"><span data-stu-id="8b108-102">ElementAt function</span></span>

<span data-ttu-id="8b108-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8b108-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8b108-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b108-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b108-105">Devuelve el en el índice especificado de una matriz.</span><span class="sxs-lookup"><span data-stu-id="8b108-105">Returns the at the given index of an array.</span></span>

```qsharp
function ElementAt<'T> (index : Int, array : 'T[]) : 'T
```


## <a name="input"></a><span data-ttu-id="8b108-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8b108-106">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="8b108-107">Índice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8b108-107">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8b108-108">Índice del elemento</span><span class="sxs-lookup"><span data-stu-id="8b108-108">Index of element</span></span>


### <a name="array--t"></a><span data-ttu-id="8b108-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="8b108-109">array : 'T[]</span></span>

<span data-ttu-id="8b108-110">Matriz que se va a indizar.</span><span class="sxs-lookup"><span data-stu-id="8b108-110">The array being indexed.</span></span>



## <a name="output--t"></a><span data-ttu-id="8b108-111">Salida: ' t</span><span class="sxs-lookup"><span data-stu-id="8b108-111">Output : 'T</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8b108-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="8b108-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8b108-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="8b108-113">'T</span></span>

<span data-ttu-id="8b108-114">Tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="8b108-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="8b108-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8b108-115">Example</span></span>

<span data-ttu-id="8b108-116">Obtiene el tercer número en cuatro secuencias enteras famosas.</span><span class="sxs-lookup"><span data-stu-id="8b108-116">Get the third number in four famous integer sequences.</span></span> <span data-ttu-id="8b108-117">(tenga en cuenta que el índice 0 corresponde al _primer_ valor de la secuencia.)</span><span class="sxs-lookup"><span data-stu-id="8b108-117">(note that the 0 index corresponds to the _first_ value of the sequence.)</span></span>

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famous2 = Mapped(ElementAt<Int>(2, _), [lucas, prime, fibonacci, catalan]);
// same as: famous2 = [3, 5, 1, 2]
```

## <a name="see-also"></a><span data-ttu-id="8b108-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b108-118">See Also</span></span>

- [<span data-ttu-id="8b108-119">Microsoft. Quantum. arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="8b108-119">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)
- [<span data-ttu-id="8b108-120">Microsoft. Quantum. arrays. ElementsAt</span><span class="sxs-lookup"><span data-stu-id="8b108-120">Microsoft.Quantum.Arrays.ElementsAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementsAt)