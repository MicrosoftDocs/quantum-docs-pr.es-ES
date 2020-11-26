---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: Operación AssertOperationsEqualInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 9b17bac9d95baf5a542604892c64130bf35d7f69
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202437"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="8ca46-102">Operación AssertOperationsEqualInPlace</span><span class="sxs-lookup"><span data-stu-id="8ca46-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="8ca46-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8ca46-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="8ca46-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8ca46-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8ca46-105">Dadas dos operaciones, garantiza que actúan de forma idéntica para todos los Estados de entrada.</span><span class="sxs-lookup"><span data-stu-id="8ca46-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="8ca46-106">Esta aserción se implementa comprobando la acción de las operaciones en todos los Estados del formulario $V _0 \otimes... \otimes V_ {n-1} $, donde $V _k $ es uno de los Estados $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ y $ \ket{i} $ (+ 1 eigenstate del operador Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="8ca46-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="8ca46-107">Esta aserción usa $n $ qubits y requiere varias llamadas de las operaciones que se van a comparar.</span><span class="sxs-lookup"><span data-stu-id="8ca46-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="8ca46-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="8ca46-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="8ca46-109">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ca46-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8ca46-110">El número de qubits $n $ en el que `givenU` operan las operaciones `expectedU` .</span><span class="sxs-lookup"><span data-stu-id="8ca46-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="8ca46-111">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8ca46-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8ca46-112">Operación en $n $ qubits que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="8ca46-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="8ca46-113">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="8ca46-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8ca46-114">Operación de referencia en $n $ qubits con la que `givenU` se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="8ca46-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ca46-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ca46-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="8ca46-116">Referencias</span><span class="sxs-lookup"><span data-stu-id="8ca46-116">References</span></span>

<span data-ttu-id="8ca46-117">La base de los Estados $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ y $ \ket{i} $ es el Chuang-Nielsen base, que se describe en [ *i. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).</span><span class="sxs-lookup"><span data-stu-id="8ca46-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="8ca46-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ca46-118">See Also</span></span>

- [<span data-ttu-id="8ca46-119">Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="8ca46-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)