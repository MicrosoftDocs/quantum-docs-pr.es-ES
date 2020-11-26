---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: Operación RippleCarryAdderD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: b87c8f25acc8854d5e8d28f58cfc99dffb92a973
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222123"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="f87dc-102">Operación RippleCarryAdderD</span><span class="sxs-lookup"><span data-stu-id="f87dc-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="f87dc-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f87dc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f87dc-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f87dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f87dc-105">Agregación reversible, en contexto, de dos enteros.</span><span class="sxs-lookup"><span data-stu-id="f87dc-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="f87dc-106">Dados dos $n enteros de $ bits codificados en registros de LittleEndian `xs` y `ys` , y un transporte de qubit, la operación calcula la suma de los dos enteros donde se conservan los bits $n $ menos significativos del resultado en `ys` y el bit de transporte es XORed a qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="f87dc-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f87dc-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="f87dc-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="f87dc-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f87dc-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f87dc-109">LittleEndian qubit registra la codificación del primer entero sumando.</span><span class="sxs-lookup"><span data-stu-id="f87dc-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="f87dc-110">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f87dc-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f87dc-111">LittleEndian qubit registra la codificación del segundo entero sumando, se modifica para contener los bits $n $ menos significativos de la suma.</span><span class="sxs-lookup"><span data-stu-id="f87dc-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="f87dc-112">transporte: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f87dc-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f87dc-113">Transportar qubit, es XORed con el bit más significativo de la suma.</span><span class="sxs-lookup"><span data-stu-id="f87dc-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f87dc-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f87dc-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f87dc-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f87dc-115">Remarks</span></span>

<span data-ttu-id="f87dc-116">La operación controlada especificada hace uso de la simetría y cancelación mutua de las operaciones para mejorar la implementación predeterminada que agrega un control a cada operación.</span><span class="sxs-lookup"><span data-stu-id="f87dc-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="f87dc-117">Referencias</span><span class="sxs-lookup"><span data-stu-id="f87dc-117">References</span></span>

- <span data-ttu-id="f87dc-118">Thomas G. Draper: "adición en un Quantum Computer", 2000.</span><span class="sxs-lookup"><span data-stu-id="f87dc-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033