---
uid: Microsoft.Quantum.Arrays.Where
title: Función Where
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219930"
---
# <a name="where-function"></a><span data-ttu-id="4ad8d-102">Función Where</span><span class="sxs-lookup"><span data-stu-id="4ad8d-102">Where function</span></span>

<span data-ttu-id="4ad8d-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4ad8d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4ad8d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4ad8d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4ad8d-105">Dado un predicado y una matriz, devuelve los índices de esa matriz donde el predicado es true.</span><span class="sxs-lookup"><span data-stu-id="4ad8d-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="4ad8d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4ad8d-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="4ad8d-107">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4ad8d-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4ad8d-108">Función de `'T` a un valor booleano que se usa para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="4ad8d-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="4ad8d-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="4ad8d-109">array : 'T[]</span></span>

<span data-ttu-id="4ad8d-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="4ad8d-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="4ad8d-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4ad8d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4ad8d-112">Matriz de índices donde `predicate` es true.</span><span class="sxs-lookup"><span data-stu-id="4ad8d-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4ad8d-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="4ad8d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4ad8d-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="4ad8d-114">'T</span></span>

<span data-ttu-id="4ad8d-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="4ad8d-115">The type of `array` elements.</span></span>