---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Operación AssertProbInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731677"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="777e0-102">Operación AssertProbInt</span><span class="sxs-lookup"><span data-stu-id="777e0-102">AssertProbInt operation</span></span>

<span data-ttu-id="777e0-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="777e0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="777e0-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="777e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="777e0-105">Valida que la probabilidad de un estado específico de un registro de Quantum tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="777e0-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="777e0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="777e0-106">Description</span></span>

<span data-ttu-id="777e0-107">Dado un $n $-qubit Quantum State $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, garantiza que la probabilidad $ | \ alpha_j | ^ 2 $ del estado $ \ket{j} $ indexada por $j $ tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="777e0-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="777e0-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="777e0-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="777e0-109">stateIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="777e0-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="777e0-110">Índice $j $ del estado $ \ket{j} $ representado por un `LittleEndian` registro.</span><span class="sxs-lookup"><span data-stu-id="777e0-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="777e0-111">se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="777e0-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="777e0-112">El valor esperado de $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="777e0-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="777e0-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="777e0-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="777e0-114">El registro qubit que almacena $ \ket{\psi} $ en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="777e0-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="777e0-115">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="777e0-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="777e0-116">Tolerancia absoluta en la diferencia entre real y expected.</span><span class="sxs-lookup"><span data-stu-id="777e0-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="777e0-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="777e0-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

