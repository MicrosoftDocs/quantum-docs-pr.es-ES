---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Función enumerada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848121"
---
# <a name="enumerated-function"></a><span data-ttu-id="4f8a7-102">Función enumerada</span><span class="sxs-lookup"><span data-stu-id="4f8a7-102">Enumerated function</span></span>

<span data-ttu-id="4f8a7-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4f8a7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4f8a7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f8a7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f8a7-105">Dada una matriz, devuelve una nueva matriz que contiene elementos de la matriz original junto con los índices de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="4f8a7-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="4f8a7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4f8a7-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="4f8a7-107">matriz: ' Telement []</span><span class="sxs-lookup"><span data-stu-id="4f8a7-107">array : 'TElement[]</span></span>

<span data-ttu-id="4f8a7-108">Una matriz cuyos elementos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="4f8a7-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="4f8a7-109">Salida: ([int](xref:microsoft.quantum.lang-ref.int), ' telement) []</span><span class="sxs-lookup"><span data-stu-id="4f8a7-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="4f8a7-110">Nueva matriz que contiene los elementos de la matriz original junto con sus índices.</span><span class="sxs-lookup"><span data-stu-id="4f8a7-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4f8a7-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="4f8a7-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="4f8a7-112">' TEle</span><span class="sxs-lookup"><span data-stu-id="4f8a7-112">'TElement</span></span>

<span data-ttu-id="4f8a7-113">Tipo de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4f8a7-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="4f8a7-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f8a7-114">Example</span></span>

<span data-ttu-id="4f8a7-115">Los `for` bucles siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="4f8a7-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```