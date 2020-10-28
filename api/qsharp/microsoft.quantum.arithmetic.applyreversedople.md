---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLE
title: Operación ApplyReversedOpLE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLE
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 0f73ac7d50e32f4467bc1683e421149fa38ee29a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731741"
---
# <a name="applyreversedople-operation"></a><span data-ttu-id="28859-102">Operación ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="28859-102">ApplyReversedOpLE operation</span></span>

<span data-ttu-id="28859-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="28859-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="28859-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="28859-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="28859-105">Aplica una operación que toma una entrada Little-Endian a un registro que codifica un entero sin signo con formato Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="28859-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="28859-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="28859-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="28859-107">OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="28859-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="28859-108">Operación que actúa en un registro Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="28859-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="28859-109">registro: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="28859-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="28859-110">Registro Big-Endian que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="28859-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="28859-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28859-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="28859-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28859-112">See Also</span></span>

- [<span data-ttu-id="28859-113">Microsoft. Quantum. aritmético. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="28859-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="28859-114">Microsoft. Quantum. aritmético. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="28859-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="28859-115">Microsoft. Quantum. aritmético. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="28859-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)