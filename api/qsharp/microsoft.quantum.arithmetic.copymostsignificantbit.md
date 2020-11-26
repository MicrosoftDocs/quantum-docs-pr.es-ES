---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operación CopyMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223296"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="fc338-102">Operación CopyMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="fc338-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="fc338-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fc338-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fc338-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc338-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc338-105">Copia el bit más significativo de un registro qubit `from` que representa un entero sin signo en el qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="fc338-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="fc338-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fc338-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="fc338-107">de: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fc338-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fc338-108">Entero sin signo del que se copia el bit más alto.</span><span class="sxs-lookup"><span data-stu-id="fc338-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="fc338-109">el entero se codifica en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="fc338-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="fc338-110">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fc338-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fc338-111">Qubit en la que se va a copiar el bit más alto.</span><span class="sxs-lookup"><span data-stu-id="fc338-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="fc338-112">La codificación de bits se basa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="fc338-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc338-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc338-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="fc338-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc338-114">See Also</span></span>

- [<span data-ttu-id="fc338-115">Microsoft. Quantum. aritmético. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="fc338-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)