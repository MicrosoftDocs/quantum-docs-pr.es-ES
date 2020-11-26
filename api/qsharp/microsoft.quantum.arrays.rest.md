---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220405"
---
# <a name="rest-function"></a><span data-ttu-id="4db73-102">Rest (función)</span><span class="sxs-lookup"><span data-stu-id="4db73-102">Rest function</span></span>

<span data-ttu-id="4db73-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4db73-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4db73-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4db73-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4db73-105">Crea una matriz que es igual a una matriz de entrada, salvo que se quita el primer elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4db73-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="4db73-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4db73-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="4db73-107">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="4db73-107">array : 'T[]</span></span>

<span data-ttu-id="4db73-108">Una matriz cuyos elementos segundo a Last van a formar la matriz de salida.</span><span class="sxs-lookup"><span data-stu-id="4db73-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="4db73-109">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="4db73-109">Output : 'T[]</span></span>

<span data-ttu-id="4db73-110">Una matriz que contiene los elementos `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="4db73-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4db73-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="4db73-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4db73-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="4db73-112">'T</span></span>

<span data-ttu-id="4db73-113">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4db73-113">The type of the array elements.</span></span>