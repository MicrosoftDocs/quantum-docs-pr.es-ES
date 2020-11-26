---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Operación AssertProbInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: b95c2c6294dd5a95b7215c22bd6c50a41635f432
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223704"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="b2d53-102">Operación AssertProbInt</span><span class="sxs-lookup"><span data-stu-id="b2d53-102">AssertProbInt operation</span></span>

<span data-ttu-id="b2d53-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b2d53-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b2d53-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2d53-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2d53-105">Valida que la probabilidad de un estado específico de un registro de Quantum tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="b2d53-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="b2d53-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2d53-106">Description</span></span>

<span data-ttu-id="b2d53-107">Dado un $n $-qubit Quantum State $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, garantiza que la probabilidad $ | \ alpha_j | ^ 2 $ del estado $ \ket{j} $ indexada por $j $ tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="b2d53-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="b2d53-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="b2d53-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="b2d53-109">stateIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b2d53-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b2d53-110">Índice $j $ del estado $ \ket{j} $ representado por un `LittleEndian` registro.</span><span class="sxs-lookup"><span data-stu-id="b2d53-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="b2d53-111">se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b2d53-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b2d53-112">El valor esperado de $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="b2d53-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="b2d53-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b2d53-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b2d53-114">El registro qubit que almacena $ \ket{\psi} $ en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="b2d53-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="b2d53-115">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b2d53-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b2d53-116">Tolerancia absoluta en la diferencia entre real y expected.</span><span class="sxs-lookup"><span data-stu-id="b2d53-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2d53-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2d53-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

