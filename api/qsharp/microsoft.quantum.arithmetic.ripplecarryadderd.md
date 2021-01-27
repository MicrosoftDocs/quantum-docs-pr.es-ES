---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: Operación RippleCarryAdderD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: f0f6f39fbff9f682f8f74a982c0a41847df1397a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842965"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="0d0bb-102">Operación RippleCarryAdderD</span><span class="sxs-lookup"><span data-stu-id="0d0bb-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="0d0bb-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0d0bb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0d0bb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d0bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d0bb-105">Agregación reversible, en contexto, de dos enteros.</span><span class="sxs-lookup"><span data-stu-id="0d0bb-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="0d0bb-106">Dados dos $n enteros de $ bits codificados en registros de LittleEndian `xs` y `ys` , y un transporte de qubit, la operación calcula la suma de los dos enteros donde se conservan los bits $n $ menos significativos del resultado en `ys` y el bit de transporte es XORed a qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="0d0bb-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0d0bb-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="0d0bb-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="0d0bb-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0d0bb-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0d0bb-109">LittleEndian qubit registra la codificación del primer entero sumando.</span><span class="sxs-lookup"><span data-stu-id="0d0bb-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="0d0bb-110">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0d0bb-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0d0bb-111">LittleEndian qubit registra la codificación del segundo entero sumando, se modifica para contener los bits $n $ menos significativos de la suma.</span><span class="sxs-lookup"><span data-stu-id="0d0bb-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="0d0bb-112">transporte: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0d0bb-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0d0bb-113">Transportar qubit, es XORed con el bit más significativo de la suma.</span><span class="sxs-lookup"><span data-stu-id="0d0bb-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0d0bb-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d0bb-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0d0bb-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0d0bb-115">Remarks</span></span>

<span data-ttu-id="0d0bb-116">La operación controlada especificada hace uso de la simetría y cancelación mutua de las operaciones para mejorar la implementación predeterminada que agrega un control a cada operación.</span><span class="sxs-lookup"><span data-stu-id="0d0bb-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="0d0bb-117">Referencias</span><span class="sxs-lookup"><span data-stu-id="0d0bb-117">References</span></span>

- <span data-ttu-id="0d0bb-118">Thomas G. Draper: "adición en un Quantum Computer", 2000.</span><span class="sxs-lookup"><span data-stu-id="0d0bb-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033