---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail, función
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 680562228a39263ef87ba053e6b7683412947e46
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845407"
---
# <a name="tail-function"></a><span data-ttu-id="0b938-102">Tail, función</span><span class="sxs-lookup"><span data-stu-id="0b938-102">Tail function</span></span>

<span data-ttu-id="0b938-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0b938-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0b938-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b938-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b938-105">Devuelve el último elemento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="0b938-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="0b938-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0b938-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="0b938-107">matriz: ' A []</span><span class="sxs-lookup"><span data-stu-id="0b938-107">array : 'A[]</span></span>

<span data-ttu-id="0b938-108">Matriz de la que se toma el último elemento.</span><span class="sxs-lookup"><span data-stu-id="0b938-108">Array of which the last element is taken.</span></span> <span data-ttu-id="0b938-109">La matriz debe tener una longitud de al menos 1.</span><span class="sxs-lookup"><span data-stu-id="0b938-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="0b938-110">Salida: ' A</span><span class="sxs-lookup"><span data-stu-id="0b938-110">Output : 'A</span></span>

<span data-ttu-id="0b938-111">Último elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="0b938-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0b938-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="0b938-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="0b938-113">' A '</span><span class="sxs-lookup"><span data-stu-id="0b938-113">'A</span></span>

<span data-ttu-id="0b938-114">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="0b938-114">The type of the array elements.</span></span>