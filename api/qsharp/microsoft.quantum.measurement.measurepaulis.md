---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Operación MeasurePaulis
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 4faaf78f24fa28ae5e4f701b80d9297c910b975e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194226"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="a8f9b-102">Operación MeasurePaulis</span><span class="sxs-lookup"><span data-stu-id="a8f9b-102">MeasurePaulis operation</span></span>

<span data-ttu-id="a8f9b-103">Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="a8f9b-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="a8f9b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8f9b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8f9b-105">Dada una matriz de operadores Pauli de varios qubit, mide cada uno de ellos con un gadget de medida especificado y, a continuación, devuelve la matriz de resultados.</span><span class="sxs-lookup"><span data-stu-id="a8f9b-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="a8f9b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a8f9b-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="a8f9b-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="a8f9b-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="a8f9b-108">Matriz de operadores de Pauli de varios qubits que se van a medir.</span><span class="sxs-lookup"><span data-stu-id="a8f9b-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a8f9b-109">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a8f9b-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a8f9b-110">Registro en el que se van a medir los operadores especificados.</span><span class="sxs-lookup"><span data-stu-id="a8f9b-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="a8f9b-111">gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="a8f9b-111">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="a8f9b-112">Operación que realiza la medición de un operador multiqubit determinado.</span><span class="sxs-lookup"><span data-stu-id="a8f9b-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="a8f9b-113">Salida: __no <Result> válido__[]</span><span class="sxs-lookup"><span data-stu-id="a8f9b-113">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="a8f9b-114">Matriz de resultados obtenida de la medición de cada elemento de `paulis` en `target` .</span><span class="sxs-lookup"><span data-stu-id="a8f9b-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>