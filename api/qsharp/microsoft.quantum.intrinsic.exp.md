---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Operación exp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 7aa6974e83e917125b63ef91fb5c3b1238f6e856
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819006"
---
# <a name="exp-operation"></a><span data-ttu-id="8db12-102">Operación exp</span><span class="sxs-lookup"><span data-stu-id="8db12-102">Exp operation</span></span>

<span data-ttu-id="8db12-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="8db12-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="8db12-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8db12-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8db12-105">Aplica el valor exponencial de un operador Pauli de varios qubit.</span><span class="sxs-lookup"><span data-stu-id="8db12-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="8db12-106">\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align} donde $P _i $ es el elemento $i $ TH de `paulis` y donde $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="8db12-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8db12-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="8db12-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="8db12-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="8db12-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="8db12-109">Matriz de valores de Pauli de qubit único que indican los factores del producto tensores en cada qubit.</span><span class="sxs-lookup"><span data-stu-id="8db12-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="8db12-110">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8db12-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8db12-111">Ángulo del operador Pauli de varios qubit determinado por el que se va a girar el registro de destino.</span><span class="sxs-lookup"><span data-stu-id="8db12-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="8db12-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8db12-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8db12-113">Regístrese para aplicar el giro determinado a.</span><span class="sxs-lookup"><span data-stu-id="8db12-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8db12-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8db12-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

