---
uid: Microsoft.Quantum.Arrays.Flattened
title: Función plana
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730261"
---
# <a name="flattened-function"></a><span data-ttu-id="c77e4-102">Función plana</span><span class="sxs-lookup"><span data-stu-id="c77e4-102">Flattened function</span></span>

<span data-ttu-id="c77e4-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c77e4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c77e4-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c77e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c77e4-105">Dada una matriz de matrices, devuelve la concatenación de todas las matrices.</span><span class="sxs-lookup"><span data-stu-id="c77e4-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="c77e4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c77e4-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="c77e4-107">matrices: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="c77e4-107">arrays : 'T[][]</span></span>

<span data-ttu-id="c77e4-108">Matriz de matrices.</span><span class="sxs-lookup"><span data-stu-id="c77e4-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="c77e4-109">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="c77e4-109">Output : 'T[]</span></span>

<span data-ttu-id="c77e4-110">Concatenación de todas las matrices.</span><span class="sxs-lookup"><span data-stu-id="c77e4-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c77e4-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c77e4-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c77e4-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="c77e4-112">'T</span></span>

<span data-ttu-id="c77e4-113">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="c77e4-113">The type of `array` elements.</span></span>