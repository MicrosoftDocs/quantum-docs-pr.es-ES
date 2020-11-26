---
uid: Microsoft.Quantum.Canon.Compose
title: Función Compose
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: f8c6ad36220b48be1723c2d91cbf7c0a4947af14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216768"
---
# <a name="compose-function"></a><span data-ttu-id="00d9d-102">Función Compose</span><span class="sxs-lookup"><span data-stu-id="00d9d-102">Compose function</span></span>

<span data-ttu-id="00d9d-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="00d9d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="00d9d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00d9d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="00d9d-105">Devuelve la composición de dos funciones.</span><span class="sxs-lookup"><span data-stu-id="00d9d-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="00d9d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="00d9d-106">Description</span></span>

<span data-ttu-id="00d9d-107">Dadas dos funciones $f $ y $g $, devuelve una nueva función que representa $f \circ g $.</span><span class="sxs-lookup"><span data-stu-id="00d9d-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="00d9d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="00d9d-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="00d9d-109">Outer: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="00d9d-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="00d9d-110">Segunda función que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="00d9d-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="00d9d-111">interno: ' U ' > ' U</span><span class="sxs-lookup"><span data-stu-id="00d9d-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="00d9d-112">La primera función que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="00d9d-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="00d9d-113">Salida: ' t-> ' V</span><span class="sxs-lookup"><span data-stu-id="00d9d-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="00d9d-114">Una nueva función $h $ tal que para todas las entradas $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="00d9d-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="00d9d-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="00d9d-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="00d9d-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="00d9d-116">'T</span></span>

<span data-ttu-id="00d9d-117">Tipo de entrada de la primera función que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="00d9d-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="00d9d-118">' U</span><span class="sxs-lookup"><span data-stu-id="00d9d-118">'U</span></span>

<span data-ttu-id="00d9d-119">El tipo de salida de la primera función que se va a aplicar y el tipo de entrada de la segunda función que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="00d9d-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="00d9d-120">' V</span><span class="sxs-lookup"><span data-stu-id="00d9d-120">'V</span></span>

<span data-ttu-id="00d9d-121">Tipo de salida de la segunda función que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="00d9d-121">The output type of the second function to be applied.</span></span>