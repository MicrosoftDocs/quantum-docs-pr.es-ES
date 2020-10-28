---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Operación AssertMeasurement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727358"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="062ff-102">Operación AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="062ff-102">AssertMeasurement operation</span></span>

<span data-ttu-id="062ff-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="062ff-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="062ff-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="062ff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="062ff-105">Las aserciones que midan el qubits determinado en la base de Pauli determinada siempre tendrán el resultado especificado.</span><span class="sxs-lookup"><span data-stu-id="062ff-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="062ff-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="062ff-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="062ff-107">bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="062ff-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="062ff-108">Un efecto de medición para imponer la probabilidad de, expresado como un operador Pauli de varios qubit.</span><span class="sxs-lookup"><span data-stu-id="062ff-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="062ff-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="062ff-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="062ff-110">Registro en el que se va a realizar la aserción.</span><span class="sxs-lookup"><span data-stu-id="062ff-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="062ff-111">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="062ff-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="062ff-112">Resultado esperado de `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="062ff-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="062ff-113">msg: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="062ff-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="062ff-114">Mensaje que se va a mostrar si se produce un error en la aserción.</span><span class="sxs-lookup"><span data-stu-id="062ff-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="062ff-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="062ff-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="062ff-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="062ff-116">Remarks</span></span>

<span data-ttu-id="062ff-117">Tenga en cuenta que las versiones contiguas y controladas de esta operación no comprobarán la condición.</span><span class="sxs-lookup"><span data-stu-id="062ff-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="062ff-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="062ff-118">See Also</span></span>

- [<span data-ttu-id="062ff-119">Microsoft. Quantum. Diagnostics. AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="062ff-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)