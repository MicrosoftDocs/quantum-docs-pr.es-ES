---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209781"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="a7288-102">RightShiftedI función)</span><span class="sxs-lookup"><span data-stu-id="a7288-102">RightShiftedI function</span></span>

<span data-ttu-id="a7288-103">Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="a7288-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="a7288-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7288-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7288-105">Desplaza la representación bit a bit de un número a la derecha un número determinado de bits.</span><span class="sxs-lookup"><span data-stu-id="a7288-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="a7288-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a7288-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="a7288-107">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a7288-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a7288-108">Número cuya representación bit a bit se va a desplazar a la derecha (menos significativa).</span><span class="sxs-lookup"><span data-stu-id="a7288-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="a7288-109">amount: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a7288-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a7288-110">Número de bits por el que `value` se va a desplazar a la derecha.</span><span class="sxs-lookup"><span data-stu-id="a7288-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="a7288-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a7288-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a7288-112">Valor de `value` , desplazado a la derecha por `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="a7288-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7288-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a7288-113">Remarks</span></span>

<span data-ttu-id="a7288-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a7288-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```