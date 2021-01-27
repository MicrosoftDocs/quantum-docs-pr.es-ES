---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Operación de medida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: bf0a606b1bfc8c4762245422450ec26907ec1946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818765"
---
# <a name="measure-operation"></a><span data-ttu-id="a879c-102">Operación de medida</span><span class="sxs-lookup"><span data-stu-id="a879c-102">Measure operation</span></span>

<span data-ttu-id="a879c-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a879c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a879c-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a879c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a879c-105">Realiza una medida conjunta de una o varias qubits en las bases de Pauli especificadas.</span><span class="sxs-lookup"><span data-stu-id="a879c-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="a879c-106">El resultado de la salida lo proporciona la distribución: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}, \end{align} donde $P _i $ es el elemento $i $ TH de `bases` y donde $N = \texttt{length} (\texttt{bases}) $.</span><span class="sxs-lookup"><span data-stu-id="a879c-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="a879c-107">Es decir, la medida devuelve un `Result` $d $ de modo que el eigenvalue del efecto de medición observado es $ (-1) ^ d $.</span><span class="sxs-lookup"><span data-stu-id="a879c-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="a879c-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="a879c-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="a879c-109">bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a879c-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="a879c-110">Matriz de valores de Pauli de qubit único que indican los factores del producto tensores en cada qubit.</span><span class="sxs-lookup"><span data-stu-id="a879c-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a879c-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a879c-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a879c-112">Registro de qubits que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="a879c-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="a879c-113">Salida: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="a879c-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="a879c-114">`Zero` Si se observa el eigenvalue $ + $1 y `One` si se observa el eigenvalue $-$1.</span><span class="sxs-lookup"><span data-stu-id="a879c-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="a879c-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a879c-115">Remarks</span></span>

<span data-ttu-id="a879c-116">Si la matriz base y la matriz qubit tienen longitudes diferentes, se producirá un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="a879c-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>