---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: Operación ApplyReversedOpBEC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 54c35ccea5e9c2d3ec7a3e6f325f78c3e602970e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731756"
---
# <a name="applyreversedopbec-operation"></a><span data-ttu-id="7cced-102">Operación ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="7cced-102">ApplyReversedOpBEC operation</span></span>

<span data-ttu-id="7cced-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7cced-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7cced-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7cced-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7cced-105">Aplica una operación que toma la entrada Big-Endian a un registro que codifica un entero sin signo con un formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="7cced-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="7cced-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7cced-106">Input</span></span>

### <a name="op--bigendian--unit-ctl"></a><span data-ttu-id="7cced-107">OP: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="7cced-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="7cced-108">Operación que actúa en un registro Big Endian.</span><span class="sxs-lookup"><span data-stu-id="7cced-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="7cced-109">registro: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7cced-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7cced-110">Registro Little-Endian que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="7cced-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7cced-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7cced-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7cced-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7cced-112">See Also</span></span>

- [<span data-ttu-id="7cced-113">Microsoft. Quantum. aritmético. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="7cced-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="7cced-114">Microsoft. Quantum. aritmético. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="7cced-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="7cced-115">Microsoft. Quantum. aritmético. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="7cced-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)