---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefixes (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845507"
---
# <a name="prefixes-function"></a><span data-ttu-id="c091e-102">Prefixes (función)</span><span class="sxs-lookup"><span data-stu-id="c091e-102">Prefixes function</span></span>

<span data-ttu-id="c091e-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c091e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c091e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c091e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c091e-105">Dada una matriz, devuelve todos sus prefijos.</span><span class="sxs-lookup"><span data-stu-id="c091e-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="c091e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c091e-106">Description</span></span>

<span data-ttu-id="c091e-107">Devuelve una matriz de todos los prefijos, empezando por una matriz que solo tiene el primer elemento hasta la matriz completa.</span><span class="sxs-lookup"><span data-stu-id="c091e-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="c091e-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="c091e-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="c091e-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="c091e-109">array : 'T[]</span></span>

<span data-ttu-id="c091e-110">Matriz de elementos.</span><span class="sxs-lookup"><span data-stu-id="c091e-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="c091e-111">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="c091e-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c091e-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c091e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c091e-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="c091e-113">'T</span></span>

<span data-ttu-id="c091e-114">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="c091e-114">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="c091e-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c091e-115">Example</span></span>

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```