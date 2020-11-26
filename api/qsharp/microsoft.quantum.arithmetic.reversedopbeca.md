---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBECA
title: ReversedOpBECA función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBECA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: da21b09110400ad4ee862f662d45e166a49e7bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222208"
---
# <a name="reversedopbeca-function"></a><span data-ttu-id="023eb-102">ReversedOpBECA función)</span><span class="sxs-lookup"><span data-stu-id="023eb-102">ReversedOpBECA function</span></span>

<span data-ttu-id="023eb-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="023eb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="023eb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="023eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="023eb-105">Dada una operación que toma una entrada big-endian, devuelve una nueva operación que toma una entrada Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="023eb-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="023eb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="023eb-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="023eb-107">OP: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) bigEndian es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="023eb-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="023eb-108">Operación cuya entrada se va a invertir.</span><span class="sxs-lookup"><span data-stu-id="023eb-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="023eb-109">Salida: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="023eb-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="023eb-110">Nueva operación que acepta su entrada como registro Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="023eb-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="023eb-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="023eb-111">See Also</span></span>

- [<span data-ttu-id="023eb-112">Microsoft. Quantum. aritmético. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="023eb-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
- [<span data-ttu-id="023eb-113">Microsoft. Quantum. aritmético. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="023eb-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="023eb-114">Microsoft. Quantum. aritmético. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="023eb-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="023eb-115">Microsoft. Quantum. aritmético. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="023eb-115">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)