---
uid: Microsoft.Quantum.Arrays.Chunks
title: Función fragmentos
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842874"
---
# <a name="chunks-function"></a><span data-ttu-id="215b1-102">Función fragmentos</span><span class="sxs-lookup"><span data-stu-id="215b1-102">Chunks function</span></span>

<span data-ttu-id="215b1-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="215b1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="215b1-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="215b1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="215b1-105">Divide una matriz en varias partes de la misma longitud.</span><span class="sxs-lookup"><span data-stu-id="215b1-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="215b1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="215b1-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="215b1-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="215b1-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="215b1-108">La longitud de cada fragmento.</span><span class="sxs-lookup"><span data-stu-id="215b1-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="215b1-109">ARR: ' t []</span><span class="sxs-lookup"><span data-stu-id="215b1-109">arr : 'T[]</span></span>

<span data-ttu-id="215b1-110">Matriz que se va a dividir.</span><span class="sxs-lookup"><span data-stu-id="215b1-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="215b1-111">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="215b1-111">Output : 'T[][]</span></span>

<span data-ttu-id="215b1-112">Una matriz que contiene cada fragmento de la matriz original.</span><span class="sxs-lookup"><span data-stu-id="215b1-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="215b1-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="215b1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="215b1-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="215b1-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="215b1-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="215b1-115">Remarks</span></span>

<span data-ttu-id="215b1-116">Tenga en cuenta que el último elemento de la salida puede ser más corto que `nElements` si `Length(arr)` no es divisible por `nElements` .</span><span class="sxs-lookup"><span data-stu-id="215b1-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>