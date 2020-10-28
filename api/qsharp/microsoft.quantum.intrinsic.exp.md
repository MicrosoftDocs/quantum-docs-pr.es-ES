---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Operación exp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: b923374a954f90aba2deaead79dd419fbf67fea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726710"
---
# <a name="exp-operation"></a><span data-ttu-id="1b40f-102">Operación exp</span><span class="sxs-lookup"><span data-stu-id="1b40f-102">Exp operation</span></span>

<span data-ttu-id="1b40f-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1b40f-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1b40f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b40f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b40f-105">Aplica el valor exponencial de un operador Pauli de varios qubit.</span><span class="sxs-lookup"><span data-stu-id="1b40f-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="1b40f-106">\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align} donde $P _i $ es el elemento $i $ TH de `paulis` y donde $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="1b40f-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1b40f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="1b40f-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="1b40f-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="1b40f-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="1b40f-109">Matriz de valores de Pauli de qubit único que indican los factores del producto tensores en cada qubit.</span><span class="sxs-lookup"><span data-stu-id="1b40f-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="1b40f-110">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1b40f-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1b40f-111">Ángulo del operador Pauli de varios qubit determinado por el que se va a girar el registro de destino.</span><span class="sxs-lookup"><span data-stu-id="1b40f-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1b40f-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1b40f-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1b40f-113">Regístrese para aplicar el giro determinado a.</span><span class="sxs-lookup"><span data-stu-id="1b40f-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1b40f-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b40f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

