---
uid: Microsoft.Quantum.Arrays.Where
title: Función Where
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 1c9fa0463ed49788d12502257d735b965565d1ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729940"
---
# <a name="where-function"></a><span data-ttu-id="948a1-102">Función Where</span><span class="sxs-lookup"><span data-stu-id="948a1-102">Where function</span></span>

<span data-ttu-id="948a1-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="948a1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="948a1-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="948a1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="948a1-105">Dado un predicado y una matriz, devuelve los índices de esa matriz donde el predicado es true.</span><span class="sxs-lookup"><span data-stu-id="948a1-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="948a1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="948a1-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="948a1-107">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="948a1-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="948a1-108">Función de `'T` a un valor booleano que se usa para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="948a1-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="948a1-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="948a1-109">array : 'T[]</span></span>

<span data-ttu-id="948a1-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="948a1-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="948a1-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="948a1-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="948a1-112">Matriz de índices donde `predicate` es true.</span><span class="sxs-lookup"><span data-stu-id="948a1-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="948a1-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="948a1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="948a1-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="948a1-114">'T</span></span>

<span data-ttu-id="948a1-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="948a1-115">The type of `array` elements.</span></span>