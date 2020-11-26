---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Operación AssertMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223789"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="6b91a-102">Operación AssertMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="6b91a-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="6b91a-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6b91a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6b91a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b91a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b91a-105">Valida que el valor de qubit más importante de un registro qubit que representa un entero sin signo está en un estado determinado.</span><span class="sxs-lookup"><span data-stu-id="6b91a-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6b91a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6b91a-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="6b91a-107">valor: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="6b91a-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="6b91a-108">Valor del bit más alto que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="6b91a-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="6b91a-109">número: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6b91a-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6b91a-110">Entero sin signo del que se comprueba el bit más alto.</span><span class="sxs-lookup"><span data-stu-id="6b91a-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b91a-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b91a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6b91a-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6b91a-112">Remarks</span></span>

<span data-ttu-id="6b91a-113">La versión controlada de esta operación omite los controles.</span><span class="sxs-lookup"><span data-stu-id="6b91a-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b91a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b91a-114">See Also</span></span>

- [<span data-ttu-id="6b91a-115">Microsoft. Quantum. Intrinsic. Assert</span><span class="sxs-lookup"><span data-stu-id="6b91a-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)