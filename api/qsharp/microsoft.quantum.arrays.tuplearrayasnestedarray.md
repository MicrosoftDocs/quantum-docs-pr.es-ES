---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729973"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="283fe-102">TupleArrayAsNestedArray función)</span><span class="sxs-lookup"><span data-stu-id="283fe-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="283fe-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="283fe-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="283fe-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="283fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="283fe-105">Convierte una lista de dos tuplas en una matriz anidada.</span><span class="sxs-lookup"><span data-stu-id="283fe-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="283fe-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="283fe-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="283fe-107">tupleList: (' t, ' t) []</span><span class="sxs-lookup"><span data-stu-id="283fe-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="283fe-108">Lista de dos tuplas que se van a convertir en una matriz anidada.</span><span class="sxs-lookup"><span data-stu-id="283fe-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="283fe-109">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="283fe-109">Output : 'T[][]</span></span>

<span data-ttu-id="283fe-110">Matriz anidada con una longitud que coincide con tupleList.</span><span class="sxs-lookup"><span data-stu-id="283fe-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="283fe-111">Ejemplo: </span><span class="sxs-lookup"><span data-stu-id="283fe-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="283fe-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="283fe-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="283fe-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="283fe-113">'T</span></span>
