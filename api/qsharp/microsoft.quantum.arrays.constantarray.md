---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210070"
---
# <a name="constantarray-function"></a><span data-ttu-id="3bd7a-102">ConstantArray función)</span><span class="sxs-lookup"><span data-stu-id="3bd7a-102">ConstantArray function</span></span>

<span data-ttu-id="3bd7a-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3bd7a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3bd7a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3bd7a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3bd7a-105">Crea una matriz de longitud determinada con todos los elementos iguales al valor especificado.</span><span class="sxs-lookup"><span data-stu-id="3bd7a-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="3bd7a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3bd7a-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="3bd7a-107">longitud: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3bd7a-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3bd7a-108">Longitud de la nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="3bd7a-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="3bd7a-109">valor: ' t</span><span class="sxs-lookup"><span data-stu-id="3bd7a-109">value : 'T</span></span>

<span data-ttu-id="3bd7a-110">Valor de cada elemento de la nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="3bd7a-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="3bd7a-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="3bd7a-111">Output : 'T[]</span></span>

<span data-ttu-id="3bd7a-112">Nueva matriz de longitud `length` , de modo que todos los elementos son `value` .</span><span class="sxs-lookup"><span data-stu-id="3bd7a-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3bd7a-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="3bd7a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3bd7a-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="3bd7a-114">'T</span></span>

