---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: Operación ApplyInnerTTKAdderWithoutCarry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 3335c63b8509090deed1172419158da0d5e80409
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731868"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="ba486-102">Operación ApplyInnerTTKAdderWithoutCarry</span><span class="sxs-lookup"><span data-stu-id="ba486-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="ba486-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ba486-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ba486-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ba486-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ba486-105">Implementa la función de suma interna para la operación RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="ba486-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="ba486-106">Se trata de la operación interna conjugada con la operación externa para construir el agregador completo.</span><span class="sxs-lookup"><span data-stu-id="ba486-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="ba486-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="ba486-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="ba486-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ba486-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ba486-109">LittleEndian qubit registra la codificación del primer entero sumando entrada en RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="ba486-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="ba486-110">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ba486-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ba486-111">LittleEndian qubit registra la codificación del segundo entero sumando entrada en RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="ba486-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ba486-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ba486-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ba486-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba486-113">Remarks</span></span>

<span data-ttu-id="ba486-114">La operación controlada especificada hace uso de la simetría y cancelación mutua de las operaciones para mejorar la implementación predeterminada que agrega un control a cada operación.</span><span class="sxs-lookup"><span data-stu-id="ba486-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="ba486-115">Referencias</span><span class="sxs-lookup"><span data-stu-id="ba486-115">References</span></span>

- <span data-ttu-id="ba486-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Additions de Quantum y ramificación sin límite", información de Quantum y cálculo, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="ba486-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530