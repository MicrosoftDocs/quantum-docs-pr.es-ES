---
uid: Microsoft.Quantum.Math.ModulusI
title: Función modulus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847301"
---
# <a name="modulusi-function"></a><span data-ttu-id="179ea-102">Función modulus</span><span class="sxs-lookup"><span data-stu-id="179ea-102">ModulusI function</span></span>

<span data-ttu-id="179ea-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="179ea-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="179ea-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="179ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="179ea-105">Calcula el residuo canónico del `value` módulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="179ea-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="179ea-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="179ea-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="179ea-107">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="179ea-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="179ea-108">Valor del que se calcula el residuo</span><span class="sxs-lookup"><span data-stu-id="179ea-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="179ea-109">módulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="179ea-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="179ea-110">El módulo por el que se toman los residuos, debe ser positivo</span><span class="sxs-lookup"><span data-stu-id="179ea-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="179ea-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="179ea-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="179ea-112">Entero $r $ entre 0 y `modulus - 1` este que `value - r` es divisible por módulo.</span><span class="sxs-lookup"><span data-stu-id="179ea-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="179ea-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="179ea-113">Remarks</span></span>

<span data-ttu-id="179ea-114">Esta función se comporta de forma diferente a cómo `%` se comporta el operador en C# y Q # como en el resultado es siempre un entero no negativo entre 0 y `modulus - 1` , incluso si el valor es negativo.</span><span class="sxs-lookup"><span data-stu-id="179ea-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>