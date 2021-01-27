---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855397"
---
# <a name="integerbits-function"></a><span data-ttu-id="0b829-102">IntegerBits función)</span><span class="sxs-lookup"><span data-stu-id="0b829-102">IntegerBits function</span></span>

<span data-ttu-id="0b829-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0b829-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0b829-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b829-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b829-105">Devuelve todas las posiciones en las que se establecen los bits de un entero.</span><span class="sxs-lookup"><span data-stu-id="0b829-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="0b829-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0b829-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="0b829-107">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0b829-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0b829-108">Un número no negativo.</span><span class="sxs-lookup"><span data-stu-id="0b829-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="0b829-109">longitud: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0b829-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0b829-110">Número de bits en la expansión binaria de `value` .</span><span class="sxs-lookup"><span data-stu-id="0b829-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="0b829-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0b829-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0b829-112">Una matriz que contiene todas las posiciones de bits (a partir de 0) que son 1 en la expansión binaria de tener en cuenta `value` todos los bits hasta la posición `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="0b829-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="0b829-113">Todas las posiciones se ordenan en la matriz por posición en un orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="0b829-113">All positions are ordered in the array by position in an increasing order.</span></span>

## <a name="example"></a><span data-ttu-id="0b829-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b829-114">Example</span></span>

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```