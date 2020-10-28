---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: Operación ApplyReversedOpBECA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 1a11b85e4eca627246d7b9d3b4c10824296e9a77
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731749"
---
# <a name="applyreversedopbeca-operation"></a><span data-ttu-id="d4ba6-102">Operación ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="d4ba6-102">ApplyReversedOpBECA operation</span></span>

<span data-ttu-id="d4ba6-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d4ba6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d4ba6-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4ba6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4ba6-105">Aplica una operación que toma la entrada Big-Endian a un registro que codifica un entero sin signo con un formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="d4ba6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d4ba6-106">Input</span></span>

### <a name="op--bigendian--unit-ctl--adj"></a><span data-ttu-id="d4ba6-107">OP: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="d4ba6-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="d4ba6-108">Operación que actúa en un registro Big Endian.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="d4ba6-109">registro: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d4ba6-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d4ba6-110">Registro Little-Endian que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4ba6-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4ba6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d4ba6-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4ba6-112">See Also</span></span>

- [<span data-ttu-id="d4ba6-113">Microsoft. Quantum. aritmético. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="d4ba6-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="d4ba6-114">Microsoft. Quantum. aritmético. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="d4ba6-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="d4ba6-115">Microsoft. Quantum. aritmético. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="d4ba6-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)