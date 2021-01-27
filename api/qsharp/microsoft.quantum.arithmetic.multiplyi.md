---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Operación de multiplicación
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 8615d0d5100c26f86264ceaecadb7783563216a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843023"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="db8e7-102">Operación de multiplicación</span><span class="sxs-lookup"><span data-stu-id="db8e7-102">MultiplyI operation</span></span>

<span data-ttu-id="db8e7-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="db8e7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="db8e7-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="db8e7-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="db8e7-105">Multiplique el entero `xs` por un entero `ys` y almacene el resultado en `result` , que debe ser cero inicialmente.</span><span class="sxs-lookup"><span data-stu-id="db8e7-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="db8e7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="db8e7-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="db8e7-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="db8e7-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="db8e7-108">$n $-bit multiplicando (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="db8e7-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="db8e7-109">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="db8e7-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="db8e7-110">$n multiplicador de $ bits (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="db8e7-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="db8e7-111">resultado: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="db8e7-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="db8e7-112">el resultado de $2N $-bit (LittleEndian) debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="db8e7-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="db8e7-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db8e7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="db8e7-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="db8e7-114">Remarks</span></span>

<span data-ttu-id="db8e7-115">Utiliza un enfoque estándar de desplazamiento y adición para implementar la multiplicación.</span><span class="sxs-lookup"><span data-stu-id="db8e7-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="db8e7-116">La versión controlada se mejoró mediante la copia de $x _i $ en una ancilla qubit condicionada en el control qubits y, a continuación, el control de la adición en el ancilla qubit.</span><span class="sxs-lookup"><span data-stu-id="db8e7-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>