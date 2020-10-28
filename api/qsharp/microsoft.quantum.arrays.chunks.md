---
uid: Microsoft.Quantum.Arrays.Chunks
title: Función fragmentos
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730413"
---
# <a name="chunks-function"></a><span data-ttu-id="a182b-102">Función fragmentos</span><span class="sxs-lookup"><span data-stu-id="a182b-102">Chunks function</span></span>

<span data-ttu-id="a182b-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a182b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a182b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a182b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a182b-105">Divide una matriz en varias partes de la misma longitud.</span><span class="sxs-lookup"><span data-stu-id="a182b-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="a182b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a182b-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="a182b-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a182b-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a182b-108">La longitud de cada fragmento.</span><span class="sxs-lookup"><span data-stu-id="a182b-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="a182b-109">ARR: ' t []</span><span class="sxs-lookup"><span data-stu-id="a182b-109">arr : 'T[]</span></span>

<span data-ttu-id="a182b-110">Matriz que se va a dividir.</span><span class="sxs-lookup"><span data-stu-id="a182b-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="a182b-111">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="a182b-111">Output : 'T[][]</span></span>

<span data-ttu-id="a182b-112">Una matriz que contiene cada fragmento de la matriz original.</span><span class="sxs-lookup"><span data-stu-id="a182b-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a182b-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="a182b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a182b-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="a182b-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="a182b-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a182b-115">Remarks</span></span>

<span data-ttu-id="a182b-116">Tenga en cuenta que el último elemento de la salida puede ser más corto que `nElements` si `Length(arr)` no es divisible por `nElements` .</span><span class="sxs-lookup"><span data-stu-id="a182b-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>