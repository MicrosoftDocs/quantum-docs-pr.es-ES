---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Operación MeasureStabilizerGenerators
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727028"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="c4b80-102">Operación MeasureStabilizerGenerators</span><span class="sxs-lookup"><span data-stu-id="c4b80-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="c4b80-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c4b80-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c4b80-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4b80-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4b80-105">Mide el conjunto dado de generadores de un grupo estabilizador.</span><span class="sxs-lookup"><span data-stu-id="c4b80-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="c4b80-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c4b80-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="c4b80-107">stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="c4b80-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="c4b80-108">Una matriz de operadores multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="c4b80-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="c4b80-109">Por ejemplo, `stabilizerGroup[0]` es una lista de matrices Pauli de un solo qubit, el producto tensores de que es un generador estabilizador.</span><span class="sxs-lookup"><span data-stu-id="c4b80-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="c4b80-110">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="c4b80-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="c4b80-111">Una matriz de qubits en la que se define el código del estabilizador.</span><span class="sxs-lookup"><span data-stu-id="c4b80-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="c4b80-112">gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="c4b80-112">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="c4b80-113">Operación que especifica cómo medir un operador multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="c4b80-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="c4b80-114">Output: [síndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="c4b80-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="c4b80-115">Resultado de las mediciones.</span><span class="sxs-lookup"><span data-stu-id="c4b80-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4b80-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c4b80-116">Remarks</span></span>

<span data-ttu-id="c4b80-117">Esto no comprueba si el conjunto de generadores dado está en el trabajo.</span><span class="sxs-lookup"><span data-stu-id="c4b80-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="c4b80-118">Si no están en el trabajo, el resultado de las medidas puede ser arbitrario.</span><span class="sxs-lookup"><span data-stu-id="c4b80-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>