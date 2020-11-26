---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 6ad3e692f68ec2d405e19a7e467ef8fe33d449fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225574"
---
# <a name="_pauliblockencoding-function"></a><span data-ttu-id="5829d-102">_PauliBlockEncoding función)</span><span class="sxs-lookup"><span data-stu-id="5829d-102">_PauliBlockEncoding function</span></span>

<span data-ttu-id="5829d-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5829d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5829d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5829d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5829d-105">Crea una unidad de codificación de bloques para un Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="5829d-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="5829d-106">El Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ se describe mediante una suma de los términos de Pauli $P _j $, cada uno con coeficiente real $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="5829d-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="5829d-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="5829d-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="5829d-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="5829d-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="5829d-109">`GeneratorSystem`Que describe $H $ como suma de los términos de Pauli</span><span class="sxs-lookup"><span data-stu-id="5829d-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>


### <a name="stateprepunitary--double---littleendian--unit--is-adj--ctl"></a><span data-ttu-id="5829d-110">statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="5829d-110">statePrepUnitary : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="5829d-111">Operación unitario $V $ que aplica la $V unitario _j $ controlada en el índice $ \ket{j} $, dada una función $f: j\rightarrow V_j $.</span><span class="sxs-lookup"><span data-stu-id="5829d-111">A unitary operation $V$ that applies the unitary $V_j$ controlled on index $\ket{j}$, given a function $f: j\rightarrow V_j$.</span></span>


### <a name="multiplexer--intint---qubit--unit--is-adj--ctl---littleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="5829d-112">multiplexor: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="5829d-112">multiplexer : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>





## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="5829d-113">Salida: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="5829d-113">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="5829d-114">Primer parámetro</span><span class="sxs-lookup"><span data-stu-id="5829d-114">First parameter</span></span>

<span data-ttu-id="5829d-115">La única norma de los coeficientes $ \alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="5829d-115">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="5829d-116">Segundo parámetro</span><span class="sxs-lookup"><span data-stu-id="5829d-116">Second parameter</span></span>

<span data-ttu-id="5829d-117">Un `BlockEncodingReflection` unitario $U $ de Hamiltonian $U $.</span><span class="sxs-lookup"><span data-stu-id="5829d-117">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $U$.</span></span> <span data-ttu-id="5829d-118">Como esta unitario cumple $U ^ 2 = I $, también es una reflexión.</span><span class="sxs-lookup"><span data-stu-id="5829d-118">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="5829d-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5829d-119">Remarks</span></span>

<span data-ttu-id="5829d-120">Operaciones de ejemplo: preparar y despreparar el estado $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $ y construir una unitario controlada por multiplicación son <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> y <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="5829d-120">Example operations the prepare and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and construct a multiply-controlled unitary are <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>