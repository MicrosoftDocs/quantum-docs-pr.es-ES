---
uid: Microsoft.Quantum.Arrays.Head
title: Head, función
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221120"
---
# <a name="head-function"></a><span data-ttu-id="b0283-102">Head, función</span><span class="sxs-lookup"><span data-stu-id="b0283-102">Head function</span></span>

<span data-ttu-id="b0283-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b0283-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b0283-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0283-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0283-105">Devuelve el primer elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b0283-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="b0283-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b0283-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="b0283-107">matriz: ' A []</span><span class="sxs-lookup"><span data-stu-id="b0283-107">array : 'A[]</span></span>

<span data-ttu-id="b0283-108">Matriz de la que se toma el primer elemento.</span><span class="sxs-lookup"><span data-stu-id="b0283-108">Array of which the first element is taken.</span></span> <span data-ttu-id="b0283-109">La matriz debe tener una longitud de al menos 1.</span><span class="sxs-lookup"><span data-stu-id="b0283-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="b0283-110">Salida: ' A</span><span class="sxs-lookup"><span data-stu-id="b0283-110">Output : 'A</span></span>

<span data-ttu-id="b0283-111">El primer elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b0283-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b0283-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="b0283-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="b0283-113">' A '</span><span class="sxs-lookup"><span data-stu-id="b0283-113">'A</span></span>

<span data-ttu-id="b0283-114">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b0283-114">The type of the array elements.</span></span>