---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 51a35555080d1d2475fc1aa9e48e84c7c6f92c51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845391"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="cf3a0-102">TupleArrayAsNestedArray función)</span><span class="sxs-lookup"><span data-stu-id="cf3a0-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="cf3a0-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cf3a0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cf3a0-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cf3a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cf3a0-105">Convierte una lista de dos tuplas en una matriz anidada.</span><span class="sxs-lookup"><span data-stu-id="cf3a0-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="cf3a0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cf3a0-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="cf3a0-107">tupleList: (' t, ' t) []</span><span class="sxs-lookup"><span data-stu-id="cf3a0-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="cf3a0-108">Lista de dos tuplas que se van a convertir en una matriz anidada.</span><span class="sxs-lookup"><span data-stu-id="cf3a0-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="cf3a0-109">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="cf3a0-109">Output : 'T[][]</span></span>

<span data-ttu-id="cf3a0-110">Matriz anidada con una longitud que coincide con tupleList.</span><span class="sxs-lookup"><span data-stu-id="cf3a0-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="cf3a0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf3a0-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="cf3a0-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="cf3a0-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cf3a0-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="cf3a0-113">'T</span></span>

