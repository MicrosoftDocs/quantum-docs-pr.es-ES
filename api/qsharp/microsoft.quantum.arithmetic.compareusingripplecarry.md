---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Operación CompareUsingRippleCarry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843284"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="e1532-102">Operación CompareUsingRippleCarry</span><span class="sxs-lookup"><span data-stu-id="e1532-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="e1532-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e1532-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e1532-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1532-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1532-105">Esta operación comprueba si un entero representado por un registro de qubits es mayor que otro entero, aplicando un XOR del resultado en una qubit de salida.</span><span class="sxs-lookup"><span data-stu-id="e1532-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e1532-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1532-106">Description</span></span>

<span data-ttu-id="e1532-107">Dado dos enteros `x` y `y` almacenados en registros de qubit de igual tamaño, esta operación comprueba si cumplen `x > y` .</span><span class="sxs-lookup"><span data-stu-id="e1532-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="e1532-108">Si es true, 1 se XORed en un qubit de salida.</span><span class="sxs-lookup"><span data-stu-id="e1532-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="e1532-109">De lo contrario, 0 se XORed en un qubit de salida.</span><span class="sxs-lookup"><span data-stu-id="e1532-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="e1532-110">En otras palabras, esta operación se puede representar mediante la unitario $ $ \begin{align} U\ket {x} \ les {y} \ les {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span><span class="sxs-lookup"><span data-stu-id="e1532-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="e1532-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="e1532-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="e1532-112">Entrada</span><span class="sxs-lookup"><span data-stu-id="e1532-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="e1532-113">x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e1532-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e1532-114">Primer número que se va a comparar en `LittleEndian` formato en un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="e1532-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="e1532-115">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e1532-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e1532-116">Segundo número que se va a comparar en el `LittleEndian` formato de un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="e1532-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="e1532-117">salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e1532-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e1532-118">Qubit que almacena el resultado de la comparación $x>y $.</span><span class="sxs-lookup"><span data-stu-id="e1532-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1532-119">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1532-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e1532-120">Referencias</span><span class="sxs-lookup"><span data-stu-id="e1532-120">References</span></span>

- <span data-ttu-id="e1532-121">Un nuevo circuito de adición de paso de onda de Quantum Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="e1532-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>