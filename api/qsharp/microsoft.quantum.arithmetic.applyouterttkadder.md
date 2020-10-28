---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: Operación ApplyOuterTTKAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: 3d6d7c3446075130e5a8ee93abbd27e617d50b3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731812"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="a9a46-102">Operación ApplyOuterTTKAdder</span><span class="sxs-lookup"><span data-stu-id="a9a46-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="a9a46-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a9a46-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a9a46-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9a46-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9a46-105">Implementa la operación externa para que RippleCarryAdderTTK conjugado la operación interna para construir el agregador completo.</span><span class="sxs-lookup"><span data-stu-id="a9a46-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="a9a46-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a9a46-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="a9a46-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a9a46-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a9a46-108">LittleEndian qubit registra la codificación del primer entero sumando entrada en RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="a9a46-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="a9a46-109">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a9a46-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a9a46-110">LittleEndian qubit registra la codificación del segundo entero sumando entrada en RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="a9a46-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9a46-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9a46-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="a9a46-112">Referencias</span><span class="sxs-lookup"><span data-stu-id="a9a46-112">References</span></span>

- <span data-ttu-id="a9a46-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Additions de Quantum y ramificación sin límite", información de Quantum y cálculo, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="a9a46-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530