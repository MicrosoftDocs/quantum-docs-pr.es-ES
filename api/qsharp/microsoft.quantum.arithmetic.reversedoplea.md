---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: b0fcf1c735bb19308a381307e64314d9d961e5da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846428"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="1f599-102">ReversedOpLEA función)</span><span class="sxs-lookup"><span data-stu-id="1f599-102">ReversedOpLEA function</span></span>

<span data-ttu-id="1f599-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1f599-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1f599-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f599-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f599-105">Dada una operación que toma una entrada Little-endian, devuelve una nueva operación que toma una entrada Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="1f599-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="1f599-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1f599-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="1f599-107">OP: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian es ADJ</span><span class="sxs-lookup"><span data-stu-id="1f599-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1f599-108">Operación cuya entrada se va a invertir.</span><span class="sxs-lookup"><span data-stu-id="1f599-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-adj"></a><span data-ttu-id="1f599-109">Salida: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) bigEndian es ADJ</span><span class="sxs-lookup"><span data-stu-id="1f599-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1f599-110">Nueva operación que acepta su entrada como registro Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="1f599-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f599-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f599-111">See Also</span></span>

- [<span data-ttu-id="1f599-112">Microsoft. Quantum. aritmético. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="1f599-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="1f599-113">Microsoft. Quantum. aritmético. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="1f599-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="1f599-114">Microsoft. Quantum. aritmético. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="1f599-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="1f599-115">Microsoft. Quantum. aritmético. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="1f599-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)