---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Operación MeasureStabilizerGenerators
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: 6c048c17df21d1026dc671f30d72a13ed8d8b7f5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200635"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="471ee-102">Operación MeasureStabilizerGenerators</span><span class="sxs-lookup"><span data-stu-id="471ee-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="471ee-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="471ee-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="471ee-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="471ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="471ee-105">Mide el conjunto dado de generadores de un grupo estabilizador.</span><span class="sxs-lookup"><span data-stu-id="471ee-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="471ee-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="471ee-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="471ee-107">stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="471ee-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="471ee-108">Una matriz de operadores multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="471ee-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="471ee-109">Por ejemplo, `stabilizerGroup[0]` es una lista de matrices Pauli de un solo qubit, el producto tensores de que es un generador estabilizador.</span><span class="sxs-lookup"><span data-stu-id="471ee-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="471ee-110">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="471ee-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="471ee-111">Una matriz de qubits en la que se define el código del estabilizador.</span><span class="sxs-lookup"><span data-stu-id="471ee-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="471ee-112">gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="471ee-112">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="471ee-113">Operación que especifica cómo medir un operador multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="471ee-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="471ee-114">Output: [síndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="471ee-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="471ee-115">Resultado de las mediciones.</span><span class="sxs-lookup"><span data-stu-id="471ee-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="471ee-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="471ee-116">Remarks</span></span>

<span data-ttu-id="471ee-117">Esto no comprueba si el conjunto de generadores dado está en el trabajo.</span><span class="sxs-lookup"><span data-stu-id="471ee-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="471ee-118">Si no están en el trabajo, el resultado de las medidas puede ser arbitrario.</span><span class="sxs-lookup"><span data-stu-id="471ee-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>