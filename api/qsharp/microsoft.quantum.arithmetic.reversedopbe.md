---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 878b0fae8a803b3136d1537309c945c052e1052c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846480"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="80852-102">ReversedOpBE función)</span><span class="sxs-lookup"><span data-stu-id="80852-102">ReversedOpBE function</span></span>

<span data-ttu-id="80852-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="80852-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="80852-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80852-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80852-105">Dada una operación que toma una entrada big-endian, devuelve una nueva operación que toma una entrada Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="80852-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="80852-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="80852-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="80852-107">OP: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="80852-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="80852-108">Operación cuya entrada se va a invertir.</span><span class="sxs-lookup"><span data-stu-id="80852-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="80852-109">Salida: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="80852-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="80852-110">Nueva operación que acepta su entrada como registro Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="80852-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="80852-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="80852-111">See Also</span></span>

- [<span data-ttu-id="80852-112">Microsoft. Quantum. aritmético. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="80852-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="80852-113">Microsoft. Quantum. aritmético. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="80852-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="80852-114">Microsoft. Quantum. aritmético. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="80852-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="80852-115">Microsoft. Quantum. aritmético. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="80852-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)