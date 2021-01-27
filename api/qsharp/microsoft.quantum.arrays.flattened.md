---
uid: Microsoft.Quantum.Arrays.Flattened
title: Función plana
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848630"
---
# <a name="flattened-function"></a><span data-ttu-id="7bad1-102">Función plana</span><span class="sxs-lookup"><span data-stu-id="7bad1-102">Flattened function</span></span>

<span data-ttu-id="7bad1-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7bad1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7bad1-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7bad1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7bad1-105">Dada una matriz de matrices, devuelve la concatenación de todas las matrices.</span><span class="sxs-lookup"><span data-stu-id="7bad1-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7bad1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7bad1-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="7bad1-107">matrices: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="7bad1-107">arrays : 'T[][]</span></span>

<span data-ttu-id="7bad1-108">Matriz de matrices.</span><span class="sxs-lookup"><span data-stu-id="7bad1-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="7bad1-109">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="7bad1-109">Output : 'T[]</span></span>

<span data-ttu-id="7bad1-110">Concatenación de todas las matrices.</span><span class="sxs-lookup"><span data-stu-id="7bad1-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7bad1-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="7bad1-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7bad1-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="7bad1-112">'T</span></span>

<span data-ttu-id="7bad1-113">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="7bad1-113">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="7bad1-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7bad1-114">Example</span></span>

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```