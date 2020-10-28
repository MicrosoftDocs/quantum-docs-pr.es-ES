---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Operación de multiplicación
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730612"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="c7961-102">Operación de multiplicación</span><span class="sxs-lookup"><span data-stu-id="c7961-102">MultiplyI operation</span></span>

<span data-ttu-id="c7961-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c7961-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c7961-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7961-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7961-105">Multiplique el entero `xs` por un entero `ys` y almacene el resultado en `result` , que debe ser cero inicialmente.</span><span class="sxs-lookup"><span data-stu-id="c7961-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="c7961-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c7961-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="c7961-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c7961-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c7961-108">$n $-bit multiplicando (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c7961-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="c7961-109">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c7961-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c7961-110">$n multiplicador de $ bits (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c7961-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="c7961-111">resultado: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c7961-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c7961-112">el resultado de $2N $-bit (LittleEndian) debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="c7961-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c7961-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7961-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c7961-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c7961-114">Remarks</span></span>

<span data-ttu-id="c7961-115">Utiliza un enfoque estándar de desplazamiento y adición para implementar la multiplicación.</span><span class="sxs-lookup"><span data-stu-id="c7961-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="c7961-116">La versión controlada se mejoró mediante la copia de $x _i $ en una ancilla qubit condicionada en el control qubits y, a continuación, el control de la adición en el ancilla qubit.</span><span class="sxs-lookup"><span data-stu-id="c7961-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>