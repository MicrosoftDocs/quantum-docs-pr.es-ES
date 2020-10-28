---
uid: Microsoft.Quantum.Math.ModulusL
title: Función modulus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733845"
---
# <a name="modulusl-function"></a><span data-ttu-id="c7b49-102">Función modulus</span><span class="sxs-lookup"><span data-stu-id="c7b49-102">ModulusL function</span></span>

<span data-ttu-id="c7b49-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c7b49-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c7b49-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7b49-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7b49-105">Calcula el residuo canónico del `value` módulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="c7b49-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="c7b49-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c7b49-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="c7b49-107">valor: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c7b49-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c7b49-108">Valor del que se calcula el residuo</span><span class="sxs-lookup"><span data-stu-id="c7b49-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="c7b49-109">módulo: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c7b49-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c7b49-110">El módulo por el que se toman los residuos, debe ser positivo</span><span class="sxs-lookup"><span data-stu-id="c7b49-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="c7b49-111">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c7b49-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c7b49-112">Entero $r $ entre 0 y `modulus - 1` este que `value - r` es divisible por módulo.</span><span class="sxs-lookup"><span data-stu-id="c7b49-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="c7b49-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c7b49-113">Remarks</span></span>

<span data-ttu-id="c7b49-114">Esta función se comporta de forma diferente a cómo `%` se comporta el operador en C# y Q # como en el resultado siempre es un entero positivo entre 0 y `modulus - 1` , incluso si el valor es negativo.</span><span class="sxs-lookup"><span data-stu-id="c7b49-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>