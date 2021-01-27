---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 014653011574d0fabb4b9aa04cedf58b87ddf798
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842155"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="1d10f-102">LeftShiftedL función)</span><span class="sxs-lookup"><span data-stu-id="1d10f-102">LeftShiftedL function</span></span>

<span data-ttu-id="1d10f-103">Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="1d10f-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="1d10f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1d10f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1d10f-105">Desplaza la representación bit a bit de un número a la izquierda de un número determinado de bits.</span><span class="sxs-lookup"><span data-stu-id="1d10f-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="1d10f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1d10f-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="1d10f-107">valor: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1d10f-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1d10f-108">Número cuya representación bit a bit se va a desplazar a la izquierda (más significativa).</span><span class="sxs-lookup"><span data-stu-id="1d10f-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="1d10f-109">amount: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d10f-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1d10f-110">Número de bits por el que `value` se va a desplazar a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="1d10f-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="1d10f-111">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1d10f-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1d10f-112">Valor de `value` , desplazado a la izquierda por `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="1d10f-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d10f-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1d10f-113">Remarks</span></span>

<span data-ttu-id="1d10f-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="1d10f-114">The following are equivalent:</span></span>

```qsharp
let c = a <<< b;
let c = LeftShiftedL(a, b);
```