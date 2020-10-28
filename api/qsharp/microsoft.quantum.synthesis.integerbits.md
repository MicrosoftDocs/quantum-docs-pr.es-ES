---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730668"
---
# <a name="integerbits-function"></a><span data-ttu-id="665e7-102">IntegerBits función)</span><span class="sxs-lookup"><span data-stu-id="665e7-102">IntegerBits function</span></span>

<span data-ttu-id="665e7-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="665e7-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="665e7-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="665e7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="665e7-105">Devuelve todas las posiciones en las que se establecen los bits de un entero.</span><span class="sxs-lookup"><span data-stu-id="665e7-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="665e7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="665e7-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="665e7-107">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="665e7-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="665e7-108">Un número no negativo.</span><span class="sxs-lookup"><span data-stu-id="665e7-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="665e7-109">longitud: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="665e7-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="665e7-110">Número de bits en la expansión binaria de `value` .</span><span class="sxs-lookup"><span data-stu-id="665e7-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="665e7-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="665e7-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="665e7-112">Una matriz que contiene todas las posiciones de bits (a partir de 0) que son 1 en la expansión binaria de tener en cuenta `value` todos los bits hasta la posición `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="665e7-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="665e7-113">Todas las posiciones se ordenan en la matriz por posición en un orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="665e7-113">All positions are ordered in the array by position in an increasing order.</span></span>