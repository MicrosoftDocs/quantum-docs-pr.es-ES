---
uid: Microsoft.Quantum.Arrays.Padded
title: Función acolchada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845561"
---
# <a name="padded-function"></a><span data-ttu-id="45d41-102">Función acolchada</span><span class="sxs-lookup"><span data-stu-id="45d41-102">Padded function</span></span>

<span data-ttu-id="45d41-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="45d41-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="45d41-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45d41-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45d41-105">Devuelve una matriz que se rellena con los valores especificados hasta una longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="45d41-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="45d41-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="45d41-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="45d41-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="45d41-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="45d41-108">Longitud de la matriz rellenada.</span><span class="sxs-lookup"><span data-stu-id="45d41-108">The length of the padded array.</span></span> <span data-ttu-id="45d41-109">Si es positivo, `inputArray` se rellena en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="45d41-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="45d41-110">Si es negativo, `inputArray` se rellena en la cola.</span><span class="sxs-lookup"><span data-stu-id="45d41-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="45d41-111">defaultElement: ' t</span><span class="sxs-lookup"><span data-stu-id="45d41-111">defaultElement : 'T</span></span>

<span data-ttu-id="45d41-112">Valor predeterminado que se va a usar para los elementos de relleno.</span><span class="sxs-lookup"><span data-stu-id="45d41-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="45d41-113">inputArray: ' t []</span><span class="sxs-lookup"><span data-stu-id="45d41-113">inputArray : 'T[]</span></span>

<span data-ttu-id="45d41-114">Matriz cuyos valores están en el encabezado de la matriz de salida.</span><span class="sxs-lookup"><span data-stu-id="45d41-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="45d41-115">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="45d41-115">Output : 'T[]</span></span>

<span data-ttu-id="45d41-116">Una matriz `output` que es el `inputArray` rellenado en el encabezado con `defaultElement` s hasta que `output` tiene la longitud `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="45d41-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="45d41-117">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="45d41-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="45d41-118">Traslada</span><span class="sxs-lookup"><span data-stu-id="45d41-118">'T</span></span>

<span data-ttu-id="45d41-119">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="45d41-119">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="45d41-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45d41-120">Example</span></span>

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```