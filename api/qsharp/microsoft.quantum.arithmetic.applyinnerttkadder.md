---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: Operación ApplyInnerTTKAdder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 1de0248066aec531d78130703414067603ffd34d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191013"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="65f49-102">Operación ApplyInnerTTKAdder</span><span class="sxs-lookup"><span data-stu-id="65f49-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="65f49-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="65f49-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="65f49-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65f49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65f49-105">Implementa la función de suma interna para la operación RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="65f49-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="65f49-106">Se trata de la operación interna conjugada con la operación externa para construir el agregador completo.</span><span class="sxs-lookup"><span data-stu-id="65f49-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="65f49-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="65f49-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="65f49-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="65f49-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="65f49-109">LittleEndian qubit registra la codificación del primer entero sumando entrada en RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="65f49-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="65f49-110">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="65f49-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="65f49-111">LittleEndian qubit registra la codificación del segundo entero sumando entrada en RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="65f49-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="65f49-112">transporte: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="65f49-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="65f49-113">Transportar qubit, es XORed con el bit más significativo de la suma.</span><span class="sxs-lookup"><span data-stu-id="65f49-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65f49-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65f49-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="65f49-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="65f49-115">Remarks</span></span>

<span data-ttu-id="65f49-116">La operación controlada especificada hace uso de la simetría y cancelación mutua de las operaciones para mejorar la implementación predeterminada que agrega un control a cada operación.</span><span class="sxs-lookup"><span data-stu-id="65f49-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="65f49-117">Referencias</span><span class="sxs-lookup"><span data-stu-id="65f49-117">References</span></span>

- <span data-ttu-id="65f49-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Additions de Quantum y ramificación sin límite", información de Quantum y cálculo, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="65f49-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530