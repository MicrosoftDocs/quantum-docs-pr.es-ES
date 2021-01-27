---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: Operación ApplyCNOTChain
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: b5a74eb66529095233c89a4ec7ea37c996458cb4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841962"
---
# <a name="applycnotchain-operation"></a><span data-ttu-id="a0c6e-102">Operación ApplyCNOTChain</span><span class="sxs-lookup"><span data-stu-id="a0c6e-102">ApplyCNOTChain operation</span></span>

<span data-ttu-id="a0c6e-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a0c6e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a0c6e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a0c6e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a0c6e-105">Calcula la paridad de un registro de qubits en contexto.</span><span class="sxs-lookup"><span data-stu-id="a0c6e-105">Computes the parity of a register of qubits in-place.</span></span>

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a0c6e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0c6e-106">Description</span></span>

<span data-ttu-id="a0c6e-107">Esta operación transforma el estado de su entrada como $ $ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_ {n-1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_ {n-1}}.</span><span class="sxs-lookup"><span data-stu-id="a0c6e-107">This operation transforms the state of its input as $$ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}.</span></span>
<span data-ttu-id="a0c6e-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a0c6e-108">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="a0c6e-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="a0c6e-109">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="a0c6e-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a0c6e-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a0c6e-111">Matriz de qubits cuya paridad se va a calcular y almacenar.</span><span class="sxs-lookup"><span data-stu-id="a0c6e-111">Array of qubits whose parity is to be computed and stored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a0c6e-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a0c6e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

