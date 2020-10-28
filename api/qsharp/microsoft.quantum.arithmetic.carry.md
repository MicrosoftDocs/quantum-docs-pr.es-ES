---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Operación de transporte
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 2b977151861fb01be7d7dbad6e0a7b803fded880
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731644"
---
# <a name="carry-operation"></a><span data-ttu-id="3e617-102">Operación de transporte</span><span class="sxs-lookup"><span data-stu-id="3e617-102">Carry operation</span></span>

<span data-ttu-id="3e617-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3e617-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3e617-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e617-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e617-105">Implementa una puerta de transporte reversible.</span><span class="sxs-lookup"><span data-stu-id="3e617-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="3e617-106">Dado un bit de transporte codificado en qubit `carryIn` y dos bits de sumando codificados en `summand1` y `summand2` , calcula la operación XOR bit a bit de `carryIn` y `summand1` `summand2` en el qubit `summand2` y el transporte se XORed a qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="3e617-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="3e617-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="3e617-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="3e617-108">transporte: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3e617-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3e617-109">Qubit de transporte.</span><span class="sxs-lookup"><span data-stu-id="3e617-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="3e617-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3e617-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3e617-111">Primer sumando qubit.</span><span class="sxs-lookup"><span data-stu-id="3e617-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="3e617-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3e617-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3e617-113">Second sumando qubit, se reemplaza por el bit más bajo de la suma de `summand1` y `summand2` .</span><span class="sxs-lookup"><span data-stu-id="3e617-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="3e617-114">carryOut: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3e617-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3e617-115">El qubit se XORed con el bit más alto de la suma.</span><span class="sxs-lookup"><span data-stu-id="3e617-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e617-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e617-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

