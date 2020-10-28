---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Operación ApplyCNOTChainWithTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729677"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="1e18a-102">Operación ApplyCNOTChainWithTarget</span><span class="sxs-lookup"><span data-stu-id="1e18a-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="1e18a-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1e18a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1e18a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e18a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e18a-105">Calcula la paridad de una matriz de qubits en un qubit de destino.</span><span class="sxs-lookup"><span data-stu-id="1e18a-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="1e18a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e18a-106">Description</span></span>

<span data-ttu-id="1e18a-107">Si la matriz está inicialmente en el estado $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{Target}}} $, el estado final lo proporciona $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{Target}}} $.</span><span class="sxs-lookup"><span data-stu-id="1e18a-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="1e18a-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="1e18a-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="1e18a-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1e18a-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1e18a-110">Matriz de qubits en la que se calcula la paridad.</span><span class="sxs-lookup"><span data-stu-id="1e18a-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="1e18a-111">targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1e18a-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1e18a-112">Qubit final en el que la paridad de "qubits" es XORed.</span><span class="sxs-lookup"><span data-stu-id="1e18a-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e18a-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e18a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1e18a-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1e18a-114">Remarks</span></span>

<span data-ttu-id="1e18a-115">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="1e18a-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="1e18a-116">y</span><span class="sxs-lookup"><span data-stu-id="1e18a-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```