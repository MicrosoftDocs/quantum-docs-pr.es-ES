---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: Operación ExpFrac
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 6634caff164c841876fb53e79c3f93254a7d624c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849415"
---
# <a name="expfrac-operation"></a><span data-ttu-id="a7e32-102">Operación ExpFrac</span><span class="sxs-lookup"><span data-stu-id="a7e32-102">ExpFrac operation</span></span>

<span data-ttu-id="a7e32-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a7e32-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a7e32-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a7e32-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a7e32-105">Aplica el valor exponencial de un operador Pauli de varios qubit con un argumento proporcionado por una fracción Dyadic.</span><span class="sxs-lookup"><span data-stu-id="a7e32-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="a7e32-106">\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align} donde $P _i $ es el elemento $i $ TH de y `paulis` donde $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="a7e32-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a7e32-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="a7e32-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="a7e32-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a7e32-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="a7e32-109">Matriz de valores de Pauli de qubit único que indican los factores del producto tensores en cada qubit.</span><span class="sxs-lookup"><span data-stu-id="a7e32-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="a7e32-110">Numerador: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a7e32-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a7e32-111">Numerador ($k $) en la representación de la fracción de Dyadic del ángulo por el que se va a girar el registro qubit.</span><span class="sxs-lookup"><span data-stu-id="a7e32-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="a7e32-112">potencia: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a7e32-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a7e32-113">Potencia de dos ($n $) que especifica el denominador del ángulo por el que se va a girar el registro qubit.</span><span class="sxs-lookup"><span data-stu-id="a7e32-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a7e32-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a7e32-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a7e32-115">Regístrese para aplicar el giro determinado a.</span><span class="sxs-lookup"><span data-stu-id="a7e32-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a7e32-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7e32-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

