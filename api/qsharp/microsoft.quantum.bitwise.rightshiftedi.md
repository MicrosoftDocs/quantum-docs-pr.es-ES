---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845251"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="34790-102">RightShiftedI función)</span><span class="sxs-lookup"><span data-stu-id="34790-102">RightShiftedI function</span></span>

<span data-ttu-id="34790-103">Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="34790-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="34790-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34790-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34790-105">Desplaza la representación bit a bit de un número a la derecha un número determinado de bits.</span><span class="sxs-lookup"><span data-stu-id="34790-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="34790-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="34790-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="34790-107">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="34790-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="34790-108">Número cuya representación bit a bit se va a desplazar a la derecha (menos significativa).</span><span class="sxs-lookup"><span data-stu-id="34790-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="34790-109">amount: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="34790-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="34790-110">Número de bits por el que `value` se va a desplazar a la derecha.</span><span class="sxs-lookup"><span data-stu-id="34790-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="34790-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="34790-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="34790-112">Valor de `value` , desplazado a la derecha por `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="34790-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="34790-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="34790-113">Remarks</span></span>

<span data-ttu-id="34790-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="34790-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```