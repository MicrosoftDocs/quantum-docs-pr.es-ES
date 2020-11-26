---
uid: Microsoft.Quantum.Arrays.Flattened
title: Función plana
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221222"
---
# <a name="flattened-function"></a><span data-ttu-id="8e2d7-102">Función plana</span><span class="sxs-lookup"><span data-stu-id="8e2d7-102">Flattened function</span></span>

<span data-ttu-id="8e2d7-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8e2d7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8e2d7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8e2d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8e2d7-105">Dada una matriz de matrices, devuelve la concatenación de todas las matrices.</span><span class="sxs-lookup"><span data-stu-id="8e2d7-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="8e2d7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8e2d7-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="8e2d7-107">matrices: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="8e2d7-107">arrays : 'T[][]</span></span>

<span data-ttu-id="8e2d7-108">Matriz de matrices.</span><span class="sxs-lookup"><span data-stu-id="8e2d7-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="8e2d7-109">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="8e2d7-109">Output : 'T[]</span></span>

<span data-ttu-id="8e2d7-110">Concatenación de todas las matrices.</span><span class="sxs-lookup"><span data-stu-id="8e2d7-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8e2d7-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="8e2d7-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8e2d7-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="8e2d7-112">'T</span></span>

<span data-ttu-id="8e2d7-113">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="8e2d7-113">The type of `array` elements.</span></span>