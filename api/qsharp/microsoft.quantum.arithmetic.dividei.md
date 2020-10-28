---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Operación de división
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731581"
---
# <a name="dividei-operation"></a><span data-ttu-id="22322-102">Operación de división</span><span class="sxs-lookup"><span data-stu-id="22322-102">DivideI operation</span></span>

<span data-ttu-id="22322-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="22322-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="22322-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22322-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22322-105">Divide dos enteros de Quantum.</span><span class="sxs-lookup"><span data-stu-id="22322-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="22322-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="22322-106">Description</span></span>

<span data-ttu-id="22322-107">`xs` mantendrá el resto `xs - floor(xs/ys) * ys` y `result` lo mantendrá `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="22322-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="22322-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="22322-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="22322-109">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="22322-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="22322-110">$n dividendo de $ bits, se reemplazará por el resto.</span><span class="sxs-lookup"><span data-stu-id="22322-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="22322-111">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="22322-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="22322-112">$n divisor de $ bits</span><span class="sxs-lookup"><span data-stu-id="22322-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="22322-113">resultado: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="22322-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="22322-114">$n resultado de $ bits, debe tener el estado $ \ket {0} $ inicialmente y se reemplazará por el resultado de la división de enteros.</span><span class="sxs-lookup"><span data-stu-id="22322-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="22322-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22322-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="22322-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="22322-116">Remarks</span></span>

<span data-ttu-id="22322-117">Utiliza un enfoque estándar de desplazamiento y resta para implementar la división.</span><span class="sxs-lookup"><span data-stu-id="22322-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="22322-118">La versión controlada está especializada, por lo que la resta no requiere controles adicionales.</span><span class="sxs-lookup"><span data-stu-id="22322-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>