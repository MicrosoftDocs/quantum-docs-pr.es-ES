---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis operación
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: e074ed2ae259f6aef49a8d327ce518a9e2caebfa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727406"
---
# <a name="_fliptobasis-operation"></a><span data-ttu-id="aa091-102">_flipToBasis operación</span><span class="sxs-lookup"><span data-stu-id="aa091-102">_flipToBasis operation</span></span>

<span data-ttu-id="aa091-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="aa091-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="aa091-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa091-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa091-105">Aplica unitaries que asigna $ \ket {0} \otimes\cdots\ket {0} $ a $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $, donde $ \ket{\ psi_k} $ depende de `basis[k]` .</span><span class="sxs-lookup"><span data-stu-id="aa091-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="aa091-106">La correspondencia entre el valor de `basis[k]` y $ \ket{\ psi_k} $ es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="aa091-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="aa091-107">`basis[k]=0` $ \rightarrow \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="aa091-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="aa091-108">`basis[k]=1` $ \rightarrow \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="aa091-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="aa091-109">`basis[k]=2` $ \rightarrow \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="aa091-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="aa091-110">`basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 eigenstate de Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="aa091-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="aa091-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="aa091-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="aa091-112">base: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="aa091-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="aa091-113">Matriz de identificadores de estado de base de un solo qubit (0 <= ID <= 3), uno para cada elemento de qubits.</span><span class="sxs-lookup"><span data-stu-id="aa091-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="aa091-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aa091-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aa091-115">Qubit en el que se va a operar.</span><span class="sxs-lookup"><span data-stu-id="aa091-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa091-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa091-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

