---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Operación de suma
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730437"
---
# <a name="sum-operation"></a><span data-ttu-id="c9405-102">Operación de suma</span><span class="sxs-lookup"><span data-stu-id="c9405-102">Sum operation</span></span>

<span data-ttu-id="c9405-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c9405-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c9405-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9405-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9405-105">Implementa una puerta de suma reversible.</span><span class="sxs-lookup"><span data-stu-id="c9405-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="c9405-106">Dado un bit de transporte codificado en qubit `carryIn` y dos bits de sumando codificados en `summand1` y `summand2` , calcula la operación XOR bit a bit de `carryIn` y `summand1` `summand2` en qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="c9405-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="c9405-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c9405-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="c9405-108">transporte: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c9405-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c9405-109">Qubit de transporte.</span><span class="sxs-lookup"><span data-stu-id="c9405-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="c9405-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c9405-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c9405-111">Primer sumando qubit.</span><span class="sxs-lookup"><span data-stu-id="c9405-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="c9405-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c9405-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c9405-113">Second sumando qubit, se reemplaza por el bit más bajo de la suma de `summand1` y `summand2` .</span><span class="sxs-lookup"><span data-stu-id="c9405-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c9405-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9405-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c9405-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c9405-115">Remarks</span></span>

<span data-ttu-id="c9405-116">A diferencia de la `Carry` operación, no calcula el bit de transporte.</span><span class="sxs-lookup"><span data-stu-id="c9405-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>