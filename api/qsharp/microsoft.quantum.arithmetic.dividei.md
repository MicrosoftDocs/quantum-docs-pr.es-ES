---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Operación de división
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 73c4e394ca38b8089b2990f8a8b6a3ee50f644d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846683"
---
# <a name="dividei-operation"></a><span data-ttu-id="43e35-102">Operación de división</span><span class="sxs-lookup"><span data-stu-id="43e35-102">DivideI operation</span></span>

<span data-ttu-id="43e35-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="43e35-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="43e35-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="43e35-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="43e35-105">Divide dos enteros de Quantum.</span><span class="sxs-lookup"><span data-stu-id="43e35-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="43e35-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="43e35-106">Description</span></span>

<span data-ttu-id="43e35-107">`xs` mantendrá el resto `xs - floor(xs/ys) * ys` y `result` lo mantendrá `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="43e35-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="43e35-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="43e35-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="43e35-109">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="43e35-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="43e35-110">$n dividendo de $ bits, se reemplazará por el resto.</span><span class="sxs-lookup"><span data-stu-id="43e35-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="43e35-111">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="43e35-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="43e35-112">$n divisor de $ bits</span><span class="sxs-lookup"><span data-stu-id="43e35-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="43e35-113">resultado: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="43e35-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="43e35-114">$n resultado de $ bits, debe tener el estado $ \ket {0} $ inicialmente y se reemplazará por el resultado de la división de enteros.</span><span class="sxs-lookup"><span data-stu-id="43e35-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="43e35-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="43e35-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="43e35-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="43e35-116">Remarks</span></span>

<span data-ttu-id="43e35-117">Utiliza un enfoque estándar de desplazamiento y resta para implementar la división.</span><span class="sxs-lookup"><span data-stu-id="43e35-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="43e35-118">La versión controlada está especializada, por lo que la resta no requiere controles adicionales.</span><span class="sxs-lookup"><span data-stu-id="43e35-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>