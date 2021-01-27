---
uid: Microsoft.Quantum.Math.ModulusL
title: Función modulus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842740"
---
# <a name="modulusl-function"></a><span data-ttu-id="d0dc5-102">Función modulus</span><span class="sxs-lookup"><span data-stu-id="d0dc5-102">ModulusL function</span></span>

<span data-ttu-id="d0dc5-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d0dc5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d0dc5-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0dc5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0dc5-105">Calcula el residuo canónico del `value` módulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="d0dc5-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="d0dc5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d0dc5-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="d0dc5-107">valor: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d0dc5-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d0dc5-108">Valor del que se calcula el residuo</span><span class="sxs-lookup"><span data-stu-id="d0dc5-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="d0dc5-109">módulo: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d0dc5-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d0dc5-110">El módulo por el que se toman los residuos, debe ser positivo</span><span class="sxs-lookup"><span data-stu-id="d0dc5-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="d0dc5-111">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d0dc5-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d0dc5-112">Entero $r $ entre 0 y `modulus - 1` este que `value - r` es divisible por módulo.</span><span class="sxs-lookup"><span data-stu-id="d0dc5-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="d0dc5-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d0dc5-113">Remarks</span></span>

<span data-ttu-id="d0dc5-114">Esta función se comporta de forma diferente a cómo `%` se comporta el operador en C# y Q # como en el resultado es siempre un entero no negativo entre 0 y `modulus - 1` , incluso si el valor es negativo.</span><span class="sxs-lookup"><span data-stu-id="d0dc5-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>