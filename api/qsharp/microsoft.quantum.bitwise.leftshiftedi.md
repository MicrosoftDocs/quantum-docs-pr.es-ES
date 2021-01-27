---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845303"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="309b4-102">LeftShiftedI función)</span><span class="sxs-lookup"><span data-stu-id="309b4-102">LeftShiftedI function</span></span>

<span data-ttu-id="309b4-103">Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="309b4-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="309b4-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="309b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="309b4-105">Desplaza la representación bit a bit de un número a la izquierda de un número determinado de bits.</span><span class="sxs-lookup"><span data-stu-id="309b4-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="309b4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="309b4-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="309b4-107">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="309b4-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="309b4-108">Número cuya representación bit a bit se va a desplazar a la izquierda (más significativa).</span><span class="sxs-lookup"><span data-stu-id="309b4-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="309b4-109">amount: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="309b4-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="309b4-110">Número de bits por el que `value` se va a desplazar a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="309b4-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="309b4-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="309b4-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="309b4-112">Valor de `value` , desplazado a la izquierda por `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="309b4-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="309b4-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="309b4-113">Remarks</span></span>

<span data-ttu-id="309b4-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="309b4-114">The following are equivalent:</span></span>

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```