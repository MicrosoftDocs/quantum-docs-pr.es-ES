---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA
title: Operación ApplyReversedOpLEA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 073ba908f2a06d36a8b73237f6a12d974b9d4d15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731740"
---
# <a name="applyreversedoplea-operation"></a><span data-ttu-id="5b8bd-102">Operación ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="5b8bd-102">ApplyReversedOpLEA operation</span></span>

<span data-ttu-id="5b8bd-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5b8bd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5b8bd-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5b8bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5b8bd-105">Aplica una operación que toma una entrada Little-Endian a un registro que codifica un entero sin signo con formato Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="5b8bd-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="5b8bd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5b8bd-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="5b8bd-107">OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) de => [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5b8bd-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="5b8bd-108">Operación que actúa en un registro Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="5b8bd-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="5b8bd-109">registro: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="5b8bd-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="5b8bd-110">Registro Big-Endian que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="5b8bd-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5b8bd-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5b8bd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5b8bd-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b8bd-112">See Also</span></span>

- [<span data-ttu-id="5b8bd-113">Microsoft. Quantum. aritmético. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="5b8bd-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="5b8bd-114">Microsoft. Quantum. aritmético. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="5b8bd-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="5b8bd-115">Microsoft. Quantum. aritmético. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="5b8bd-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)