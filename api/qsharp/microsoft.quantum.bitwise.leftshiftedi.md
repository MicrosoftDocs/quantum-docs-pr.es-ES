---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729877"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="82f13-102">LeftShiftedI función)</span><span class="sxs-lookup"><span data-stu-id="82f13-102">LeftShiftedI function</span></span>

<span data-ttu-id="82f13-103">Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="82f13-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="82f13-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82f13-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82f13-105">Desplaza la representación bit a bit de un número a la izquierda de un número determinado de bits.</span><span class="sxs-lookup"><span data-stu-id="82f13-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="82f13-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="82f13-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="82f13-107">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82f13-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82f13-108">Número cuya representación bit a bit se va a desplazar a la izquierda (más significativa).</span><span class="sxs-lookup"><span data-stu-id="82f13-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="82f13-109">amount: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82f13-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82f13-110">Número de bits por el que `value` se va a desplazar a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="82f13-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="82f13-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82f13-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82f13-112">Valor de `value` , desplazado a la izquierda por `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="82f13-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="82f13-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="82f13-113">Remarks</span></span>

<span data-ttu-id="82f13-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="82f13-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```