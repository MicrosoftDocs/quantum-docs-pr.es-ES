---
uid: Microsoft.Quantum.Arrays.Where
title: Función Where
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842214"
---
# <a name="where-function"></a><span data-ttu-id="f0a16-102">Función Where</span><span class="sxs-lookup"><span data-stu-id="f0a16-102">Where function</span></span>

<span data-ttu-id="f0a16-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f0a16-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f0a16-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0a16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0a16-105">Dado un predicado y una matriz, devuelve los índices de esa matriz donde el predicado es true.</span><span class="sxs-lookup"><span data-stu-id="f0a16-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="f0a16-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f0a16-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="f0a16-107">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f0a16-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f0a16-108">Función de `'T` a un valor booleano que se usa para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="f0a16-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="f0a16-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="f0a16-109">array : 'T[]</span></span>

<span data-ttu-id="f0a16-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="f0a16-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="f0a16-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f0a16-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f0a16-112">Matriz de índices donde `predicate` es true.</span><span class="sxs-lookup"><span data-stu-id="f0a16-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f0a16-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="f0a16-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f0a16-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="f0a16-114">'T</span></span>

<span data-ttu-id="f0a16-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="f0a16-115">The type of `array` elements.</span></span>