---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846170"
---
# <a name="emptyarray-function"></a><span data-ttu-id="91aa2-102">EmptyArray función)</span><span class="sxs-lookup"><span data-stu-id="91aa2-102">EmptyArray function</span></span>

<span data-ttu-id="91aa2-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="91aa2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="91aa2-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="91aa2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="91aa2-105">Devuelve la matriz vacía de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="91aa2-105">Returns the empty array of a given type.</span></span>

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a><span data-ttu-id="91aa2-106">Salida: ' Telement []</span><span class="sxs-lookup"><span data-stu-id="91aa2-106">Output : 'TElement[]</span></span>

<span data-ttu-id="91aa2-107">Matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="91aa2-107">The empty array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="91aa2-108">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="91aa2-108">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="91aa2-109">' TEle</span><span class="sxs-lookup"><span data-stu-id="91aa2-109">'TElement</span></span>

<span data-ttu-id="91aa2-110">Tipo de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="91aa2-110">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="91aa2-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91aa2-111">Example</span></span>

```qsharp
let empty = EmptyArray<Int>();
```