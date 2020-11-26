---
uid: Microsoft.Quantum.Math.ModulusI
title: Función modulus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227784"
---
# <a name="modulusi-function"></a><span data-ttu-id="39168-102">Función modulus</span><span class="sxs-lookup"><span data-stu-id="39168-102">ModulusI function</span></span>

<span data-ttu-id="39168-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="39168-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="39168-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39168-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39168-105">Calcula el residuo canónico del `value` módulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="39168-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="39168-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="39168-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="39168-107">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39168-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39168-108">Valor del que se calcula el residuo</span><span class="sxs-lookup"><span data-stu-id="39168-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="39168-109">módulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39168-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39168-110">El módulo por el que se toman los residuos, debe ser positivo</span><span class="sxs-lookup"><span data-stu-id="39168-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="39168-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39168-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39168-112">Entero $r $ entre 0 y `modulus - 1` este que `value - r` es divisible por módulo.</span><span class="sxs-lookup"><span data-stu-id="39168-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="39168-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="39168-113">Remarks</span></span>

<span data-ttu-id="39168-114">Esta función se comporta de forma diferente a cómo `%` se comporta el operador en C# y Q # como en el resultado siempre es un entero positivo entre 0 y `modulus - 1` , incluso si el valor es negativo.</span><span class="sxs-lookup"><span data-stu-id="39168-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>