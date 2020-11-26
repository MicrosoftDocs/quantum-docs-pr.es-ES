---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 00d4f9151c620e044074930933ea2912b52534ed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219675"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="aeb44-102">LeftShiftedL función)</span><span class="sxs-lookup"><span data-stu-id="aeb44-102">LeftShiftedL function</span></span>

<span data-ttu-id="aeb44-103">Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="aeb44-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="aeb44-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aeb44-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aeb44-105">Desplaza la representación bit a bit de un número a la izquierda de un número determinado de bits.</span><span class="sxs-lookup"><span data-stu-id="aeb44-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="aeb44-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="aeb44-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="aeb44-107">valor: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="aeb44-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="aeb44-108">Número cuya representación bit a bit se va a desplazar a la izquierda (más significativa).</span><span class="sxs-lookup"><span data-stu-id="aeb44-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="aeb44-109">amount: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aeb44-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aeb44-110">Número de bits por el que `value` se va a desplazar a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="aeb44-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="aeb44-111">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="aeb44-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="aeb44-112">Valor de `value` , desplazado a la izquierda por `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="aeb44-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="aeb44-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="aeb44-113">Remarks</span></span>

<span data-ttu-id="aeb44-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="aeb44-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```