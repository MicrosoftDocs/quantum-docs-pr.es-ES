---
uid: Microsoft.Quantum.Arrays.Reversed
title: Función invertida
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730044"
---
# <a name="reversed-function"></a><span data-ttu-id="a4cc6-102">Función invertida</span><span class="sxs-lookup"><span data-stu-id="a4cc6-102">Reversed function</span></span>

<span data-ttu-id="a4cc6-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a4cc6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a4cc6-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a4cc6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a4cc6-105">Cree una matriz que contenga los mismos elementos que una matriz de entrada, pero en orden inverso.</span><span class="sxs-lookup"><span data-stu-id="a4cc6-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a4cc6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a4cc6-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="a4cc6-107">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="a4cc6-107">array : 'T[]</span></span>

<span data-ttu-id="a4cc6-108">Una matriz cuyos elementos se van a copiar en orden inverso.</span><span class="sxs-lookup"><span data-stu-id="a4cc6-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="a4cc6-109">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="a4cc6-109">Output : 'T[]</span></span>

<span data-ttu-id="a4cc6-110">Una matriz que contiene los elementos `array[Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="a4cc6-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="a4cc6-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="a4cc6-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a4cc6-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="a4cc6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a4cc6-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="a4cc6-113">'T</span></span>

<span data-ttu-id="a4cc6-114">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="a4cc6-114">The type of the array elements.</span></span>