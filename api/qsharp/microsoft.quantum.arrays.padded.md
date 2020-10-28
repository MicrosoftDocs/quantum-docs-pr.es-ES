---
uid: Microsoft.Quantum.Arrays.Padded
title: Función acolchada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730092"
---
# <a name="padded-function"></a><span data-ttu-id="8e91a-102">Función acolchada</span><span class="sxs-lookup"><span data-stu-id="8e91a-102">Padded function</span></span>

<span data-ttu-id="8e91a-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8e91a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8e91a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8e91a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8e91a-105">Devuelve una matriz que se rellena con los valores especificados hasta una longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="8e91a-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="8e91a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8e91a-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="8e91a-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8e91a-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8e91a-108">Longitud de la matriz rellenada.</span><span class="sxs-lookup"><span data-stu-id="8e91a-108">The length of the padded array.</span></span> <span data-ttu-id="8e91a-109">Si es positivo, `inputArray` se rellena en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="8e91a-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="8e91a-110">Si es negativo, `inputArray` se rellena en la cola.</span><span class="sxs-lookup"><span data-stu-id="8e91a-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="8e91a-111">defaultElement: ' t</span><span class="sxs-lookup"><span data-stu-id="8e91a-111">defaultElement : 'T</span></span>

<span data-ttu-id="8e91a-112">Valor predeterminado que se va a usar para los elementos de relleno.</span><span class="sxs-lookup"><span data-stu-id="8e91a-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="8e91a-113">inputArray: ' t []</span><span class="sxs-lookup"><span data-stu-id="8e91a-113">inputArray : 'T[]</span></span>

<span data-ttu-id="8e91a-114">Matriz cuyos valores están en el encabezado de la matriz de salida.</span><span class="sxs-lookup"><span data-stu-id="8e91a-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="8e91a-115">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="8e91a-115">Output : 'T[]</span></span>

<span data-ttu-id="8e91a-116">Una matriz `output` que es el `inputArray` rellenado en el encabezado con `defaultElement` s hasta que `output` tiene la longitud `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="8e91a-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8e91a-117">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="8e91a-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8e91a-118">Traslada</span><span class="sxs-lookup"><span data-stu-id="8e91a-118">'T</span></span>

<span data-ttu-id="8e91a-119">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="8e91a-119">The type of the array elements.</span></span>