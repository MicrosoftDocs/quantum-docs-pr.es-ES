---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Operación AssertMeasurementProbability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830817"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="16794-102">Operación AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="16794-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="16794-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="16794-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="16794-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="16794-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="16794-105">Las aserciones que midan el qubits determinado en la base de Pauli determinada tendrán el resultado dado con la probabilidad especificada, dentro de cierta tolerancia.</span><span class="sxs-lookup"><span data-stu-id="16794-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="16794-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="16794-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="16794-107">bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="16794-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="16794-108">Un efecto de medición para imponer la probabilidad de, expresado como un operador Pauli de varios qubit.</span><span class="sxs-lookup"><span data-stu-id="16794-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="16794-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="16794-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="16794-110">Registro en el que se va a realizar la aserción.</span><span class="sxs-lookup"><span data-stu-id="16794-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="16794-111">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="16794-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="16794-112">Resultado esperado de `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="16794-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="16794-113">probabilidad: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="16794-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="16794-114">La probabilidad con la que se espera el resultado especificado.</span><span class="sxs-lookup"><span data-stu-id="16794-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="16794-115">msg: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="16794-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="16794-116">Mensaje que se va a mostrar si se produce un error en la aserción.</span><span class="sxs-lookup"><span data-stu-id="16794-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="16794-117">Tol: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="16794-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="16794-118">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16794-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="16794-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16794-119">Example</span></span>

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a><span data-ttu-id="16794-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="16794-120">Remarks</span></span>

<span data-ttu-id="16794-121">Tenga en cuenta que las versiones contiguas y controladas de esta operación no comprobarán la condición.</span><span class="sxs-lookup"><span data-stu-id="16794-121">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="16794-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="16794-122">See Also</span></span>

- [<span data-ttu-id="16794-123">Microsoft. Quantum. Diagnostics. AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="16794-123">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)