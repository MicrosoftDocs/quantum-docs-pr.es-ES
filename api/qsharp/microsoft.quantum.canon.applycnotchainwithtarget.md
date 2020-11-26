---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Operación ApplyCNOTChainWithTarget
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: 8ec85ce5805b3bbd1e1f7c739f27de3a861bc79e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219114"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="44c39-102">Operación ApplyCNOTChainWithTarget</span><span class="sxs-lookup"><span data-stu-id="44c39-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="44c39-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="44c39-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="44c39-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44c39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44c39-105">Calcula la paridad de una matriz de qubits en un qubit de destino.</span><span class="sxs-lookup"><span data-stu-id="44c39-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="44c39-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="44c39-106">Description</span></span>

<span data-ttu-id="44c39-107">Si la matriz está inicialmente en el estado $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{Target}}} $, el estado final lo proporciona $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{Target}}} $.</span><span class="sxs-lookup"><span data-stu-id="44c39-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="44c39-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="44c39-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="44c39-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="44c39-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="44c39-110">Matriz de qubits en la que se calcula la paridad.</span><span class="sxs-lookup"><span data-stu-id="44c39-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="44c39-111">targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="44c39-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="44c39-112">Qubit final en el que la paridad de "qubits" es XORed.</span><span class="sxs-lookup"><span data-stu-id="44c39-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44c39-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44c39-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="44c39-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44c39-114">Remarks</span></span>

<span data-ttu-id="44c39-115">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="44c39-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="44c39-116">y</span><span class="sxs-lookup"><span data-stu-id="44c39-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```