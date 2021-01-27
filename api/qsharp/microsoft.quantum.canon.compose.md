---
uid: Microsoft.Quantum.Canon.Compose
title: Función Compose
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840905"
---
# <a name="compose-function"></a><span data-ttu-id="ada2e-102">Función Compose</span><span class="sxs-lookup"><span data-stu-id="ada2e-102">Compose function</span></span>

<span data-ttu-id="ada2e-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ada2e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ada2e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ada2e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ada2e-105">Devuelve la composición de dos funciones.</span><span class="sxs-lookup"><span data-stu-id="ada2e-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="ada2e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ada2e-106">Description</span></span>

<span data-ttu-id="ada2e-107">Dadas dos funciones $f $ y $g $, devuelve una nueva función que representa $f \circ g $.</span><span class="sxs-lookup"><span data-stu-id="ada2e-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="ada2e-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="ada2e-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="ada2e-109">Outer: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="ada2e-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="ada2e-110">Segunda función que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="ada2e-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="ada2e-111">interno: ' U ' > ' U</span><span class="sxs-lookup"><span data-stu-id="ada2e-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="ada2e-112">La primera función que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="ada2e-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="ada2e-113">Salida: ' t-> ' V</span><span class="sxs-lookup"><span data-stu-id="ada2e-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="ada2e-114">Una nueva función $h $ tal que para todas las entradas $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="ada2e-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ada2e-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ada2e-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ada2e-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="ada2e-116">'T</span></span>

<span data-ttu-id="ada2e-117">Tipo de entrada de la primera función que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="ada2e-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="ada2e-118">' U</span><span class="sxs-lookup"><span data-stu-id="ada2e-118">'U</span></span>

<span data-ttu-id="ada2e-119">El tipo de salida de la primera función que se va a aplicar y el tipo de entrada de la segunda función que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="ada2e-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="ada2e-120">' V</span><span class="sxs-lookup"><span data-stu-id="ada2e-120">'V</span></span>

<span data-ttu-id="ada2e-121">Tipo de salida de la segunda función que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="ada2e-121">The output type of the second function to be applied.</span></span>