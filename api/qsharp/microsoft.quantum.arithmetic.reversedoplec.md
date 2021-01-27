---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 2dc6a596970f909af9c329dbe7002c165854cfec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846376"
---
# <a name="reversedoplec-function"></a><span data-ttu-id="6e8ed-102">ReversedOpLEC función)</span><span class="sxs-lookup"><span data-stu-id="6e8ed-102">ReversedOpLEC function</span></span>

<span data-ttu-id="6e8ed-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6e8ed-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6e8ed-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e8ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e8ed-105">Dada una operación que toma una entrada Little-endian, devuelve una nueva operación que toma una entrada Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="6e8ed-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6e8ed-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="6e8ed-107">OP: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian es CTL</span><span class="sxs-lookup"><span data-stu-id="6e8ed-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="6e8ed-108">Operación cuya entrada se va a invertir.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-ctl"></a><span data-ttu-id="6e8ed-109">Salida: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) bigEndian es CTL</span><span class="sxs-lookup"><span data-stu-id="6e8ed-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="6e8ed-110">Nueva operación que acepta su entrada como registro Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e8ed-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e8ed-111">See Also</span></span>

- [<span data-ttu-id="6e8ed-112">Microsoft. Quantum. aritmético. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="6e8ed-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="6e8ed-113">Microsoft. Quantum. aritmético. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="6e8ed-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="6e8ed-114">Microsoft. Quantum. aritmético. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="6e8ed-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="6e8ed-115">Microsoft. Quantum. aritmético. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="6e8ed-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)