---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Operación AssertMostSignificantBit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731692"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="2b952-102">Operación AssertMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="2b952-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="2b952-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2b952-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2b952-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b952-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b952-105">Valida que el valor de qubit más importante de un registro qubit que representa un entero sin signo está en un estado determinado.</span><span class="sxs-lookup"><span data-stu-id="2b952-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="2b952-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2b952-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="2b952-107">valor: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="2b952-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="2b952-108">Valor del bit más alto que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="2b952-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="2b952-109">número: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2b952-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2b952-110">Entero sin signo del que se comprueba el bit más alto.</span><span class="sxs-lookup"><span data-stu-id="2b952-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b952-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b952-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2b952-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2b952-112">Remarks</span></span>

<span data-ttu-id="2b952-113">La versión controlada de esta operación omite los controles.</span><span class="sxs-lookup"><span data-stu-id="2b952-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b952-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b952-114">See Also</span></span>

- [<span data-ttu-id="2b952-115">Microsoft. Quantum. Intrinsic. Assert</span><span class="sxs-lookup"><span data-stu-id="2b952-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)