---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Operación de multiplicación
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 96922f0147788b37cc9bace5154288a722d4ba95
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222514"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="779ad-102">Operación de multiplicación</span><span class="sxs-lookup"><span data-stu-id="779ad-102">MultiplyI operation</span></span>

<span data-ttu-id="779ad-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="779ad-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="779ad-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="779ad-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="779ad-105">Multiplique el entero `xs` por un entero `ys` y almacene el resultado en `result` , que debe ser cero inicialmente.</span><span class="sxs-lookup"><span data-stu-id="779ad-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="779ad-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="779ad-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="779ad-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="779ad-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="779ad-108">$n $-bit multiplicando (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="779ad-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="779ad-109">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="779ad-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="779ad-110">$n multiplicador de $ bits (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="779ad-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="779ad-111">resultado: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="779ad-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="779ad-112">el resultado de $2N $-bit (LittleEndian) debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="779ad-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="779ad-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="779ad-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="779ad-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="779ad-114">Remarks</span></span>

<span data-ttu-id="779ad-115">Utiliza un enfoque estándar de desplazamiento y adición para implementar la multiplicación.</span><span class="sxs-lookup"><span data-stu-id="779ad-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="779ad-116">La versión controlada se mejoró mediante la copia de $x _i $ en una ancilla qubit condicionada en el control qubits y, a continuación, el control de la adición en el ancilla qubit.</span><span class="sxs-lookup"><span data-stu-id="779ad-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>