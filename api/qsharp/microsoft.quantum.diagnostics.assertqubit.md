---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: Operación AssertQubit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727317"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="258d0-102">Operación AssertQubit</span><span class="sxs-lookup"><span data-stu-id="258d0-102">AssertQubit operation</span></span>

<span data-ttu-id="258d0-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="258d0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="258d0-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="258d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="258d0-105">Valida que qubit `q` está en el eigenstate esperado del operador Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="258d0-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="258d0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="258d0-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="258d0-107">esperado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="258d0-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="258d0-108">El estado en el que se espera que esté el qubit: `Zero` o `One` .</span><span class="sxs-lookup"><span data-stu-id="258d0-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="258d0-109">p: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="258d0-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="258d0-110">Qubit cuyo estado se declara.</span><span class="sxs-lookup"><span data-stu-id="258d0-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="258d0-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="258d0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="258d0-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="258d0-112">Remarks</span></span>

<span data-ttu-id="258d0-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permite la aserción de Estados de qubit arbitrarios en lugar de solo $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="258d0-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="258d0-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="258d0-114">See Also</span></span>

- [<span data-ttu-id="258d0-115">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="258d0-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)