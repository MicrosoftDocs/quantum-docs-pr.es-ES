---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Operación CompareUsingRippleCarry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: 842e7ded1e38f4f6e01e79d2758e30afb85dd349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731620"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="21ba8-102">Operación CompareUsingRippleCarry</span><span class="sxs-lookup"><span data-stu-id="21ba8-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="21ba8-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="21ba8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="21ba8-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="21ba8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="21ba8-105">Esta operación comprueba si un entero representado por un registro de qubits es mayor que otro entero, aplicando un XOR del resultado en una qubit de salida.</span><span class="sxs-lookup"><span data-stu-id="21ba8-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="21ba8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="21ba8-106">Description</span></span>

<span data-ttu-id="21ba8-107">Dado dos enteros `x` y `y` almacenados en registros de qubit de igual tamaño, esta operación comprueba si cumplen `x > y` .</span><span class="sxs-lookup"><span data-stu-id="21ba8-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="21ba8-108">Si es true, 1 se XORed en un qubit de salida.</span><span class="sxs-lookup"><span data-stu-id="21ba8-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="21ba8-109">De lo contrario, 0 se XORed en un qubit de salida.</span><span class="sxs-lookup"><span data-stu-id="21ba8-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="21ba8-110">En otras palabras, esta operación se puede representar mediante la unitario $ $ \begin{align} U\ket {x} \ les {y} \ les {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span><span class="sxs-lookup"><span data-stu-id="21ba8-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="21ba8-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="21ba8-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="21ba8-112">Entrada</span><span class="sxs-lookup"><span data-stu-id="21ba8-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="21ba8-113">x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="21ba8-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="21ba8-114">Primer número que se va a comparar en `LittleEndian` formato en un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="21ba8-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="21ba8-115">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="21ba8-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="21ba8-116">Segundo número que se va a comparar en el `LittleEndian` formato de un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="21ba8-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="21ba8-117">salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="21ba8-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="21ba8-118">Qubit que almacena el resultado de la comparación $x>y $.</span><span class="sxs-lookup"><span data-stu-id="21ba8-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="21ba8-119">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="21ba8-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="21ba8-120">Referencias</span><span class="sxs-lookup"><span data-stu-id="21ba8-120">References</span></span>

- <span data-ttu-id="21ba8-121">Un nuevo circuito de adición de paso de onda de Quantum Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="21ba8-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>