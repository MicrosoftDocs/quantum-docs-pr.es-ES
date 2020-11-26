---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: c058243db2b4cee3a72e025b084b4f98f7020a6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222072"
---
# <a name="reversedopleca-function"></a><span data-ttu-id="a7451-102">ReversedOpLECA función)</span><span class="sxs-lookup"><span data-stu-id="a7451-102">ReversedOpLECA function</span></span>

<span data-ttu-id="a7451-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a7451-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a7451-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7451-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7451-105">Dada una operación que toma una entrada Little-endian, devuelve una nueva operación que toma una entrada Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="a7451-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="a7451-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a7451-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="a7451-107">OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="a7451-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a7451-108">Operación cuya entrada se va a invertir.</span><span class="sxs-lookup"><span data-stu-id="a7451-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="a7451-109">Salida: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) bigEndian es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="a7451-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a7451-110">Nueva operación que acepta su entrada como registro Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="a7451-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7451-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7451-111">See Also</span></span>

- [<span data-ttu-id="a7451-112">Microsoft. Quantum. aritmético. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="a7451-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [<span data-ttu-id="a7451-113">Microsoft. Quantum. aritmético. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="a7451-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="a7451-114">Microsoft. Quantum. aritmético. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="a7451-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="a7451-115">Microsoft. Quantum. aritmético. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="a7451-115">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)