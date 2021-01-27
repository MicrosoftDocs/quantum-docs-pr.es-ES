---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Operación AssertProbInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843405"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="6d843-102">Operación AssertProbInt</span><span class="sxs-lookup"><span data-stu-id="6d843-102">AssertProbInt operation</span></span>

<span data-ttu-id="6d843-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6d843-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6d843-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6d843-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6d843-105">Valida que la probabilidad de un estado específico de un registro de Quantum tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="6d843-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="6d843-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d843-106">Description</span></span>

<span data-ttu-id="6d843-107">Dado un $n $-qubit Quantum State $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, garantiza que la probabilidad $ | \ alpha_j | ^ 2 $ del estado $ \ket{j} $ indexada por $j $ tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="6d843-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="6d843-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="6d843-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="6d843-109">stateIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6d843-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6d843-110">Índice $j $ del estado $ \ket{j} $ representado por un `LittleEndian` registro.</span><span class="sxs-lookup"><span data-stu-id="6d843-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="6d843-111">se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6d843-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6d843-112">El valor esperado de $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="6d843-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="6d843-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6d843-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6d843-114">El registro qubit que almacena $ \ket{\psi} $ en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="6d843-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="6d843-115">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6d843-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6d843-116">Tolerancia absoluta en la diferencia entre real y expected.</span><span class="sxs-lookup"><span data-stu-id="6d843-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6d843-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6d843-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="6d843-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d843-118">Example</span></span>

<span data-ttu-id="6d843-119">Supongamos que el `qubits` registro codifica un estado de Quantum 3-qubit $ \ket{\psi} = \ sqrt {1/8} \ les {0} + \ sqrt {7/8} \ les {6} $ en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="6d843-119">Suppose that the `qubits` register encodes a 3-qubit quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{6}$ in little-endian format.</span></span>
<span data-ttu-id="6d843-120">Esto significa que el número indica $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ y $ \ket {6} \equiv\ket {0} \ket {1} {1} $.</span><span class="sxs-lookup"><span data-stu-id="6d843-120">This means that the number states $\ket{0}\equiv\ket{0}\ket{0}\ket{0}$ and $\ket{6}\equiv\ket{0}\ket{1}\ket{1}$.</span></span> <span data-ttu-id="6d843-121">A continuación, se realizan correctamente las siguientes aserciones:</span><span class="sxs-lookup"><span data-stu-id="6d843-121">Then the following asserts succeed:</span></span>

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```