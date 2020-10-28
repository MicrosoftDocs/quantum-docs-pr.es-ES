---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: Operación ApplyReversedOpBEA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: f606011dd002d6eadc4f882005f4577aeb28cac0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731757"
---
# <a name="applyreversedopbea-operation"></a><span data-ttu-id="7eb06-102">Operación ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="7eb06-102">ApplyReversedOpBEA operation</span></span>

<span data-ttu-id="7eb06-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7eb06-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7eb06-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7eb06-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7eb06-105">Aplica una operación que toma la entrada Big-Endian a un registro que codifica un entero sin signo con un formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="7eb06-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="7eb06-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7eb06-106">Input</span></span>

### <a name="op--bigendian--unit-adj"></a><span data-ttu-id="7eb06-107">OP: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) de => [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7eb06-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7eb06-108">Operación que actúa en un registro Big Endian.</span><span class="sxs-lookup"><span data-stu-id="7eb06-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="7eb06-109">registro: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7eb06-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7eb06-110">Registro Little-Endian que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="7eb06-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7eb06-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7eb06-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7eb06-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7eb06-112">See Also</span></span>

- [<span data-ttu-id="7eb06-113">Microsoft. Quantum. aritmético. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="7eb06-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="7eb06-114">Microsoft. Quantum. aritmético. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="7eb06-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="7eb06-115">Microsoft. Quantum. aritmético. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="7eb06-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)