---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730045"
---
# <a name="rest-function"></a><span data-ttu-id="d7d9e-102">Rest (función)</span><span class="sxs-lookup"><span data-stu-id="d7d9e-102">Rest function</span></span>

<span data-ttu-id="d7d9e-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d7d9e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d7d9e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7d9e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7d9e-105">Crea una matriz que es igual a una matriz de entrada, salvo que se quita el primer elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="d7d9e-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d7d9e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d7d9e-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="d7d9e-107">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="d7d9e-107">array : 'T[]</span></span>

<span data-ttu-id="d7d9e-108">Una matriz cuyos elementos segundo a Last van a formar la matriz de salida.</span><span class="sxs-lookup"><span data-stu-id="d7d9e-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="d7d9e-109">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="d7d9e-109">Output : 'T[]</span></span>

<span data-ttu-id="d7d9e-110">Una matriz que contiene los elementos `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="d7d9e-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d7d9e-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d7d9e-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d7d9e-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="d7d9e-112">'T</span></span>

<span data-ttu-id="d7d9e-113">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="d7d9e-113">The type of the array elements.</span></span>