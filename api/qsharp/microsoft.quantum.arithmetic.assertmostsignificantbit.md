---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Operación AssertMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843419"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="ad932-102">Operación AssertMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="ad932-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="ad932-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ad932-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ad932-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad932-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad932-105">Valida que el valor de qubit más importante de un registro qubit que representa un entero sin signo está en un estado determinado.</span><span class="sxs-lookup"><span data-stu-id="ad932-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ad932-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ad932-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="ad932-107">valor: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="ad932-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="ad932-108">Valor del bit más alto que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="ad932-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="ad932-109">número: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ad932-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ad932-110">Entero sin signo del que se comprueba el bit más alto.</span><span class="sxs-lookup"><span data-stu-id="ad932-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad932-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad932-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ad932-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ad932-112">Remarks</span></span>

<span data-ttu-id="ad932-113">La versión controlada de esta operación omite los controles.</span><span class="sxs-lookup"><span data-stu-id="ad932-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad932-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad932-114">See Also</span></span>

- [<span data-ttu-id="ad932-115">Microsoft. Quantum. Intrinsic. Assert</span><span class="sxs-lookup"><span data-stu-id="ad932-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)