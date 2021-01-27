---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d02817e5372b841f3ab633cafa22af603c5310c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846391"
---
# <a name="reversedople-function"></a><span data-ttu-id="f4dd2-102">ReversedOpLE función)</span><span class="sxs-lookup"><span data-stu-id="f4dd2-102">ReversedOpLE function</span></span>

<span data-ttu-id="f4dd2-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f4dd2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f4dd2-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4dd2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4dd2-105">Dada una operación que toma una entrada Little-endian, devuelve una nueva operación que toma una entrada Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="f4dd2-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="f4dd2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f4dd2-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="f4dd2-107">OP: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="f4dd2-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f4dd2-108">Operación cuya entrada se va a invertir.</span><span class="sxs-lookup"><span data-stu-id="f4dd2-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="f4dd2-109">Salida: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="f4dd2-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f4dd2-110">Nueva operación que acepta su entrada como registro Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="f4dd2-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4dd2-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4dd2-111">See Also</span></span>

- [<span data-ttu-id="f4dd2-112">Microsoft. Quantum. aritmético. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="f4dd2-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="f4dd2-113">Microsoft. Quantum. aritmético. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="f4dd2-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="f4dd2-114">Microsoft. Quantum. aritmético. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="f4dd2-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="f4dd2-115">Microsoft. Quantum. aritmético. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="f4dd2-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)