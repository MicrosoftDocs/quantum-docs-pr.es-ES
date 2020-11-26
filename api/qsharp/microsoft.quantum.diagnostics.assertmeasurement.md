---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Operación AssertMeasurement
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 3fbe000202abbd8a206b0c83dfa35f4546ea91cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202454"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="524c7-102">Operación AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="524c7-102">AssertMeasurement operation</span></span>

<span data-ttu-id="524c7-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="524c7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="524c7-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="524c7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="524c7-105">Las aserciones que midan el qubits determinado en la base de Pauli determinada siempre tendrán el resultado especificado.</span><span class="sxs-lookup"><span data-stu-id="524c7-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="524c7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="524c7-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="524c7-107">bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="524c7-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="524c7-108">Un efecto de medición para imponer la probabilidad de, expresado como un operador Pauli de varios qubit.</span><span class="sxs-lookup"><span data-stu-id="524c7-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="524c7-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="524c7-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="524c7-110">Registro en el que se va a realizar la aserción.</span><span class="sxs-lookup"><span data-stu-id="524c7-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="524c7-111">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="524c7-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="524c7-112">Resultado esperado de `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="524c7-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="524c7-113">msg: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="524c7-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="524c7-114">Mensaje que se va a mostrar si se produce un error en la aserción.</span><span class="sxs-lookup"><span data-stu-id="524c7-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="524c7-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="524c7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="524c7-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="524c7-116">Remarks</span></span>

<span data-ttu-id="524c7-117">Tenga en cuenta que las versiones contiguas y controladas de esta operación no comprobarán la condición.</span><span class="sxs-lookup"><span data-stu-id="524c7-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="524c7-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="524c7-118">See Also</span></span>

- [<span data-ttu-id="524c7-119">Microsoft. Quantum. Diagnostics. AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="524c7-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)