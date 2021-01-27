---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Operación AssertQubitWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 7f57fc7a29d3eb86dc94cb24230d52b37eb6971d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853429"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="0c4ed-102">Operación AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="0c4ed-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="0c4ed-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0c4ed-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0c4ed-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0c4ed-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0c4ed-105">Valida que qubit `q` está en el eigenstate esperado del operador Pauli Z hasta una tolerancia determinada.</span><span class="sxs-lookup"><span data-stu-id="0c4ed-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="0c4ed-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0c4ed-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="0c4ed-107">esperado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="0c4ed-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="0c4ed-108">El estado en el que se espera que esté el qubit: `Zero` o `One` .</span><span class="sxs-lookup"><span data-stu-id="0c4ed-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="0c4ed-109">p: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0c4ed-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0c4ed-110">Qubit cuyo estado se declara.</span><span class="sxs-lookup"><span data-stu-id="0c4ed-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="0c4ed-111">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0c4ed-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0c4ed-112">Tolerancia en la probabilidad de que una medida de qubit devuelva el resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="0c4ed-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c4ed-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c4ed-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0c4ed-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0c4ed-114">Remarks</span></span>

<span data-ttu-id="0c4ed-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permite la aserción de Estados de qubit arbitrarios en lugar de solo $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="0c4ed-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c4ed-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c4ed-116">See Also</span></span>

- [<span data-ttu-id="0c4ed-117">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="0c4ed-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)