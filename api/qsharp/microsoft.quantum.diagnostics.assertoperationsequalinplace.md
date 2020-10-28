---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: Operación AssertOperationsEqualInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727329"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="7fbb6-102">Operación AssertOperationsEqualInPlace</span><span class="sxs-lookup"><span data-stu-id="7fbb6-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="7fbb6-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7fbb6-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7fbb6-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7fbb6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7fbb6-105">Dadas dos operaciones, garantiza que actúan de forma idéntica para todos los Estados de entrada.</span><span class="sxs-lookup"><span data-stu-id="7fbb6-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="7fbb6-106">Esta aserción se implementa comprobando la acción de las operaciones en todos los Estados del formulario $V _0 \otimes... \otimes V_ {n-1} $, donde $V _k $ es uno de los Estados $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ y $ \ket{i} $ (+ 1 eigenstate del operador Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="7fbb6-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="7fbb6-107">Esta aserción usa $n $ qubits y requiere varias llamadas de las operaciones que se van a comparar.</span><span class="sxs-lookup"><span data-stu-id="7fbb6-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="7fbb6-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="7fbb6-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="7fbb6-109">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7fbb6-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7fbb6-110">El número de qubits $n $ en el que `givenU` operan las operaciones `expectedU` .</span><span class="sxs-lookup"><span data-stu-id="7fbb6-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="7fbb6-111">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="7fbb6-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7fbb6-112">Operación en $n $ qubits que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="7fbb6-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="7fbb6-113">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7fbb6-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7fbb6-114">Operación de referencia en $n $ qubits con la que `givenU` se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="7fbb6-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7fbb6-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7fbb6-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="7fbb6-116">Referencias</span><span class="sxs-lookup"><span data-stu-id="7fbb6-116">References</span></span>

<span data-ttu-id="7fbb6-117">La base de los Estados $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ y $ \ket{i} $ es el Chuang-Nielsen base, que se describe en [ *i. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).</span><span class="sxs-lookup"><span data-stu-id="7fbb6-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="7fbb6-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7fbb6-118">See Also</span></span>

- [<span data-ttu-id="7fbb6-119">Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="7fbb6-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)