---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 392b97171bcfb9d35a38189fc9c27e61cf9cf7d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846468"
---
# <a name="reversedopbea-function"></a><span data-ttu-id="f5910-102">ReversedOpBEA función)</span><span class="sxs-lookup"><span data-stu-id="f5910-102">ReversedOpBEA function</span></span>

<span data-ttu-id="f5910-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f5910-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f5910-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5910-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5910-105">Dada una operación que toma una entrada big-endian, devuelve una nueva operación que toma una entrada Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="f5910-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="f5910-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f5910-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj"></a><span data-ttu-id="f5910-107">OP: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) bigEndian es ADJ</span><span class="sxs-lookup"><span data-stu-id="f5910-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f5910-108">Operación cuya entrada se va a invertir.</span><span class="sxs-lookup"><span data-stu-id="f5910-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-adj"></a><span data-ttu-id="f5910-109">Salida: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian es ADJ</span><span class="sxs-lookup"><span data-stu-id="f5910-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f5910-110">Nueva operación que acepta su entrada como registro Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="f5910-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5910-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5910-111">See Also</span></span>

- [<span data-ttu-id="f5910-112">Microsoft. Quantum. aritmético. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="f5910-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="f5910-113">Microsoft. Quantum. aritmético. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="f5910-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="f5910-114">Microsoft. Quantum. aritmético. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="f5910-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="f5910-115">Microsoft. Quantum. aritmético. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="f5910-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)