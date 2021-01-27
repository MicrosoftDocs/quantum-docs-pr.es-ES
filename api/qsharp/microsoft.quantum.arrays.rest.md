---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845472"
---
# <a name="rest-function"></a><span data-ttu-id="e3e41-102">Rest (función)</span><span class="sxs-lookup"><span data-stu-id="e3e41-102">Rest function</span></span>

<span data-ttu-id="e3e41-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e3e41-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e3e41-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3e41-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3e41-105">Crea una matriz que es igual a una matriz de entrada, salvo que se quita el primer elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="e3e41-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e3e41-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e3e41-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="e3e41-107">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="e3e41-107">array : 'T[]</span></span>

<span data-ttu-id="e3e41-108">Una matriz cuyos elementos segundo a Last van a formar la matriz de salida.</span><span class="sxs-lookup"><span data-stu-id="e3e41-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="e3e41-109">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="e3e41-109">Output : 'T[]</span></span>

<span data-ttu-id="e3e41-110">Una matriz que contiene los elementos `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="e3e41-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e3e41-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="e3e41-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e3e41-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="e3e41-112">'T</span></span>

<span data-ttu-id="e3e41-113">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="e3e41-113">The type of the array elements.</span></span>