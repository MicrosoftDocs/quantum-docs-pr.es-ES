---
uid: Microsoft.Quantum.Arrays.Head
title: Head, función
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848567"
---
# <a name="head-function"></a><span data-ttu-id="9aab9-102">Head, función</span><span class="sxs-lookup"><span data-stu-id="9aab9-102">Head function</span></span>

<span data-ttu-id="9aab9-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9aab9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9aab9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9aab9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9aab9-105">Devuelve el primer elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="9aab9-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="9aab9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9aab9-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="9aab9-107">matriz: ' A []</span><span class="sxs-lookup"><span data-stu-id="9aab9-107">array : 'A[]</span></span>

<span data-ttu-id="9aab9-108">Matriz de la que se toma el primer elemento.</span><span class="sxs-lookup"><span data-stu-id="9aab9-108">Array of which the first element is taken.</span></span> <span data-ttu-id="9aab9-109">La matriz debe tener una longitud de al menos 1.</span><span class="sxs-lookup"><span data-stu-id="9aab9-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="9aab9-110">Salida: ' A</span><span class="sxs-lookup"><span data-stu-id="9aab9-110">Output : 'A</span></span>

<span data-ttu-id="9aab9-111">El primer elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="9aab9-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9aab9-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="9aab9-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="9aab9-113">' A '</span><span class="sxs-lookup"><span data-stu-id="9aab9-113">'A</span></span>

<span data-ttu-id="9aab9-114">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="9aab9-114">The type of the array elements.</span></span>