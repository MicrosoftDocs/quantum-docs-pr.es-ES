---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: Operación ApplyReversedOpLEC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: ac9a6000140445a457a9abc46d5143dcb089883e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731733"
---
# <a name="applyreversedoplec-operation"></a><span data-ttu-id="aa19d-102">Operación ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="aa19d-102">ApplyReversedOpLEC operation</span></span>

<span data-ttu-id="aa19d-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="aa19d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="aa19d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa19d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa19d-105">Aplica una operación que toma una entrada Little-Endian a un registro que codifica un entero sin signo con formato Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="aa19d-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="aa19d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="aa19d-106">Input</span></span>

### <a name="op--littleendian--unit-ctl"></a><span data-ttu-id="aa19d-107">OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="aa19d-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="aa19d-108">Operación que actúa en un registro Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="aa19d-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="aa19d-109">registro: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="aa19d-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="aa19d-110">Registro Big-Endian que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="aa19d-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa19d-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa19d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="aa19d-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa19d-112">See Also</span></span>

- [<span data-ttu-id="aa19d-113">Microsoft. Quantum. aritmético. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="aa19d-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="aa19d-114">Microsoft. Quantum. aritmético. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="aa19d-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="aa19d-115">Microsoft. Quantum. aritmético. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="aa19d-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)