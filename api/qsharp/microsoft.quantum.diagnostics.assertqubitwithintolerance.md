---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Operación AssertQubitWithinTolerance
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 3fe4aa739c5e15199401aecb76ef551e52f6dcff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727292"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="67d87-102">Operación AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="67d87-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="67d87-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="67d87-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="67d87-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="67d87-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="67d87-105">Valida que qubit `q` está en el eigenstate esperado del operador Pauli Z hasta una tolerancia determinada.</span><span class="sxs-lookup"><span data-stu-id="67d87-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="67d87-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="67d87-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="67d87-107">esperado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="67d87-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="67d87-108">El estado en el que se espera que esté el qubit: `Zero` o `One` .</span><span class="sxs-lookup"><span data-stu-id="67d87-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="67d87-109">p: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="67d87-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="67d87-110">Qubit cuyo estado se declara.</span><span class="sxs-lookup"><span data-stu-id="67d87-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="67d87-111">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="67d87-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="67d87-112">Tolerancia en la probabilidad de que una medida de qubit devuelva el resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="67d87-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="67d87-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67d87-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="67d87-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="67d87-114">Remarks</span></span>

<span data-ttu-id="67d87-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permite la aserción de Estados de qubit arbitrarios en lugar de solo $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="67d87-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="67d87-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67d87-116">See Also</span></span>

- [<span data-ttu-id="67d87-117">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="67d87-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)