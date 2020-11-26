---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Función enumerada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221426"
---
# <a name="enumerated-function"></a><span data-ttu-id="d44ae-102">Función enumerada</span><span class="sxs-lookup"><span data-stu-id="d44ae-102">Enumerated function</span></span>

<span data-ttu-id="d44ae-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d44ae-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d44ae-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d44ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d44ae-105">Dada una matriz, devuelve una nueva matriz que contiene elementos de la matriz original junto con los índices de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="d44ae-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="d44ae-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d44ae-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="d44ae-107">matriz: ' Telement []</span><span class="sxs-lookup"><span data-stu-id="d44ae-107">array : 'TElement[]</span></span>

<span data-ttu-id="d44ae-108">Una matriz cuyos elementos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="d44ae-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="d44ae-109">Salida: ([int](xref:microsoft.quantum.lang-ref.int), ' telement) []</span><span class="sxs-lookup"><span data-stu-id="d44ae-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="d44ae-110">Nueva matriz que contiene los elementos de la matriz original junto con sus índices.</span><span class="sxs-lookup"><span data-stu-id="d44ae-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d44ae-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d44ae-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="d44ae-112">' TEle</span><span class="sxs-lookup"><span data-stu-id="d44ae-112">'TElement</span></span>

<span data-ttu-id="d44ae-113">Tipo de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="d44ae-113">The type of elements of the array.</span></span>