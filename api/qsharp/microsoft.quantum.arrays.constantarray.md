---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730380"
---
# <a name="constantarray-function"></a><span data-ttu-id="ba03d-102">ConstantArray función)</span><span class="sxs-lookup"><span data-stu-id="ba03d-102">ConstantArray function</span></span>

<span data-ttu-id="ba03d-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ba03d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ba03d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ba03d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ba03d-105">Crea una matriz de longitud determinada con todos los elementos iguales al valor especificado.</span><span class="sxs-lookup"><span data-stu-id="ba03d-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ba03d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ba03d-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="ba03d-107">longitud: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ba03d-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ba03d-108">Longitud de la nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="ba03d-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="ba03d-109">valor: ' t</span><span class="sxs-lookup"><span data-stu-id="ba03d-109">value : 'T</span></span>

<span data-ttu-id="ba03d-110">Valor de cada elemento de la nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="ba03d-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="ba03d-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="ba03d-111">Output : 'T[]</span></span>

<span data-ttu-id="ba03d-112">Nueva matriz de longitud `length` , de modo que todos los elementos son `value` .</span><span class="sxs-lookup"><span data-stu-id="ba03d-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ba03d-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ba03d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ba03d-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="ba03d-114">'T</span></span>

