---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: Operación ApplyCNOTChain
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: e237e4424661de816e73b0c78523180b41190cf9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219148"
---
# <a name="applycnotchain-operation"></a><span data-ttu-id="64c9b-102">Operación ApplyCNOTChain</span><span class="sxs-lookup"><span data-stu-id="64c9b-102">ApplyCNOTChain operation</span></span>

<span data-ttu-id="64c9b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="64c9b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="64c9b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64c9b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64c9b-105">Calcula la paridad de un registro de qubits en contexto.</span><span class="sxs-lookup"><span data-stu-id="64c9b-105">Computes the parity of a register of qubits in-place.</span></span>

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="64c9b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="64c9b-106">Description</span></span>

<span data-ttu-id="64c9b-107">Esta operación transforma el estado de su entrada como $ $ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_ {n-1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_ {n-1}}.</span><span class="sxs-lookup"><span data-stu-id="64c9b-107">This operation transforms the state of its input as $$ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}.</span></span>
<span data-ttu-id="64c9b-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="64c9b-108">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="64c9b-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="64c9b-109">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="64c9b-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="64c9b-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="64c9b-111">Matriz de qubits cuya paridad se va a calcular y almacenar.</span><span class="sxs-lookup"><span data-stu-id="64c9b-111">Array of qubits whose parity is to be computed and stored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="64c9b-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="64c9b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

