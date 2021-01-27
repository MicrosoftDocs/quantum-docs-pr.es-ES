---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848518"
---
# <a name="indexof-function"></a><span data-ttu-id="c5258-102">IndexOf (función)</span><span class="sxs-lookup"><span data-stu-id="c5258-102">IndexOf function</span></span>

<span data-ttu-id="c5258-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c5258-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c5258-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5258-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5258-105">Devuelve el primer índice del primer elemento de una matriz que satisface un predicado determinado.</span><span class="sxs-lookup"><span data-stu-id="c5258-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="c5258-106">Si no existe ningún elemento de este tipo, devuelve-1.</span><span class="sxs-lookup"><span data-stu-id="c5258-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="c5258-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c5258-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="c5258-108">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c5258-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c5258-109">Función de predicado que actúa sobre los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="c5258-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="c5258-110">ARR: ' t []</span><span class="sxs-lookup"><span data-stu-id="c5258-110">arr : 'T[]</span></span>

<span data-ttu-id="c5258-111">Matriz en la que se va a buscar mediante el predicado especificado.</span><span class="sxs-lookup"><span data-stu-id="c5258-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="c5258-112">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5258-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5258-113">El índice más pequeño, `idx` tal que `predicate(arr[idx])` sea true, o-1 si no existe ese elemento.</span><span class="sxs-lookup"><span data-stu-id="c5258-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c5258-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c5258-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c5258-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="c5258-115">'T</span></span>



## <a name="example"></a><span data-ttu-id="c5258-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5258-116">Example</span></span>

<span data-ttu-id="c5258-117">Supongamos que `IsEven : Int -> Bool` es una función que devuelve `true` solo si su entrada es par.</span><span class="sxs-lookup"><span data-stu-id="c5258-117">Suppose that `IsEven : Int -> Bool` is a function that returns `true` if and only if its input is even.</span></span> <span data-ttu-id="c5258-118">A continuación, se puede usar con `IndexOf` para buscar el primer elemento par en una matriz:</span><span class="sxs-lookup"><span data-stu-id="c5258-118">Then, this can be used with `IndexOf` to find the first even element in an array:</span></span>

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```