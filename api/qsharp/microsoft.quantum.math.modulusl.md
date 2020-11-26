---
uid: Microsoft.Quantum.Math.ModulusL
title: Función modulus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 5c9a8ceceac5d2cdac6b82f7f74a85e9443382a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194940"
---
# <a name="modulusl-function"></a><span data-ttu-id="3f19d-102">Función modulus</span><span class="sxs-lookup"><span data-stu-id="3f19d-102">ModulusL function</span></span>

<span data-ttu-id="3f19d-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3f19d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3f19d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3f19d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3f19d-105">Calcula el residuo canónico del `value` módulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="3f19d-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="3f19d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3f19d-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="3f19d-107">valor: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3f19d-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3f19d-108">Valor del que se calcula el residuo</span><span class="sxs-lookup"><span data-stu-id="3f19d-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="3f19d-109">módulo: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3f19d-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3f19d-110">El módulo por el que se toman los residuos, debe ser positivo</span><span class="sxs-lookup"><span data-stu-id="3f19d-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="3f19d-111">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3f19d-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3f19d-112">Entero $r $ entre 0 y `modulus - 1` este que `value - r` es divisible por módulo.</span><span class="sxs-lookup"><span data-stu-id="3f19d-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="3f19d-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3f19d-113">Remarks</span></span>

<span data-ttu-id="3f19d-114">Esta función se comporta de forma diferente a cómo `%` se comporta el operador en C# y Q # como en el resultado siempre es un entero positivo entre 0 y `modulus - 1` , incluso si el valor es negativo.</span><span class="sxs-lookup"><span data-stu-id="3f19d-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>