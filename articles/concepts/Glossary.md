---
title: Glosario de Quantum Computing
description: Un glosario de términos, acciones y objetos comunes que se usan en la informática Quantum.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 2a3b1fe480b9886d0c11255bb1b1e01402dce4f7
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630104"
---
# <a name="quantum-computing-glossary"></a><span data-ttu-id="1e0d9-103">Glosario de Quantum Computing</span><span class="sxs-lookup"><span data-stu-id="1e0d9-103">Quantum computing glossary</span></span>

## <a name="adjoint"></a><span data-ttu-id="1e0d9-104">Contiguo</span><span class="sxs-lookup"><span data-stu-id="1e0d9-104">Adjoint</span></span>

<span data-ttu-id="1e0d9-105">La transposición de conjugada compleja de una [operación](xref:microsoft.quantum.glossary#operation).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-105">The complex conjugate transpose of an [operation](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="1e0d9-106">En el caso de las operaciones que implementan un operador [unitario](xref:microsoft.quantum.glossary#unitary-operator) , el signo contiguo es el inverso de la operación y se indica mediante un símbolo Cruz.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-106">For operations that implement a [unitary](xref:microsoft.quantum.glossary#unitary-operator) operator, the adjoint is the inverse of the operation and is indicated by a dagger symbol.</span></span> <span data-ttu-id="1e0d9-107">Por ejemplo, si la operación `U` representa el operador unitario $U $ , `Adjoint U` representa $U ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="1e0d9-107">For example, if the operation `U` represents the unitary operator $U$, then `Adjoint U` represents $U^\dagger$.</span></span> <span data-ttu-id="1e0d9-108">Para obtener más información, [vea el](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-108">For more information, see [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="ancilla"></a><span data-ttu-id="1e0d9-109">Ancilla</span><span class="sxs-lookup"><span data-stu-id="1e0d9-109">Ancilla</span></span>

<span data-ttu-id="1e0d9-110">Un [qubit](xref:microsoft.quantum.glossary#qubit) que actúa como memoria temporal para un equipo Quantum y que se asigna y se anula la asignación según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-110">A [qubit](xref:microsoft.quantum.glossary#qubit) that serves as temporary memory for a quantum computer and is allocated and de-allocated as needed.</span></span>  <span data-ttu-id="1e0d9-111">Para obtener más información, vea [varios qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-111">For more information, see [Multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

## <a name="bell-state"></a><span data-ttu-id="1e0d9-112">Estado de campana</span><span class="sxs-lookup"><span data-stu-id="1e0d9-112">Bell state</span></span>

<span data-ttu-id="1e0d9-113">Uno de los cuatro Estados de [entangled](xref:microsoft.quantum.glossary#entanglement) [Quantum](xref:microsoft.quantum.glossary#quantum-state) con un estado máximo de dos qubits.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-113">One of four specific maximally [entangled](xref:microsoft.quantum.glossary#entanglement) [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two qubits.</span></span> <span data-ttu-id="1e0d9-114">Los cuatro Estados se definen como $ \ket { \ beta_ {ij } } = (\Mathbb{I } \Otimes X ^ iz ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-114">The four states are defined $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="1e0d9-115">Un estado de campana también se conoce como un [par de EPR](xref:microsoft.quantum.glossary#epr-pair).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-115">A Bell state is also known as an [EPR pair](xref:microsoft.quantum.glossary#epr-pair).</span></span>

## <a name="bloch-sphere"></a><span data-ttu-id="1e0d9-116">Esfera Bloch</span><span class="sxs-lookup"><span data-stu-id="1e0d9-116">Bloch sphere</span></span>

<span data-ttu-id="1e0d9-117">Representación gráfica de un [Estado de cuanto](xref:microsoft.quantum.glossary#quantum-state) de un solo[qubit](xref:microsoft.quantum.glossary#qubit) como punto en una esfera de unidad tridimensional.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-117">A graphical representation of a single-[qubit](xref:microsoft.quantum.glossary#qubit) [quantum state](xref:microsoft.quantum.glossary#quantum-state) as a point in a three-dimensional unit sphere.</span></span> <span data-ttu-id="1e0d9-118">Para obtener más información, vea [visualizar qubits y transformaciones mediante la esfera Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-118">For more information, see  [Visualizing Qubits and Transformations using the Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

## <a name="callable"></a><span data-ttu-id="1e0d9-119">Llamadas</span><span class="sxs-lookup"><span data-stu-id="1e0d9-119">Callable</span></span>

<span data-ttu-id="1e0d9-120">[Operación](xref:microsoft.quantum.glossary#operation) o [función](xref:microsoft.quantum.glossary#function) en el lenguaje de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-120">An [operation](xref:microsoft.quantum.glossary#operation) or [function](xref:microsoft.quantum.glossary#function) in the Q# language.</span></span> <span data-ttu-id="1e0d9-121">Para obtener más información, vea [operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-121">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="clifford-group"></a><span data-ttu-id="1e0d9-122">Grupo Clifford</span><span class="sxs-lookup"><span data-stu-id="1e0d9-122">Clifford group</span></span>

<span data-ttu-id="1e0d9-123">Conjunto de operaciones que ocupan el octants de la [esfera Bloch](xref:microsoft.quantum.glossary#bloch-sphere) y las permutaciones de efecto de los [operadores Pauli](xref:microsoft.quantum.glossary#pauli-operators).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-123">The set of operations that occupy the octants of the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere) and effect permutations of the [Pauli operators](xref:microsoft.quantum.glossary#pauli-operators).</span></span> <span data-ttu-id="1e0d9-124">Entre ellas se incluyen las operaciones [$X $ ](xref:microsoft.quantum.intrinsic.x), [$Y $ ](xref:microsoft.quantum.intrinsic.y), [$Z $ ](xref:microsoft.quantum.intrinsic.z), [$H $ ](xref:microsoft.quantum.intrinsic.h) y [$S $ ](xref:microsoft.quantum.intrinsic.s).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-124">These include the operations [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$](xref:microsoft.quantum.intrinsic.y), [$Z$](xref:microsoft.quantum.intrinsic.z), [$H$](xref:microsoft.quantum.intrinsic.h) and [$S$](xref:microsoft.quantum.intrinsic.s).</span></span>

## <a name="controlled"></a><span data-ttu-id="1e0d9-125">Regula</span><span class="sxs-lookup"><span data-stu-id="1e0d9-125">Controlled</span></span>

<span data-ttu-id="1e0d9-126">Una [operación](xref:microsoft.quantum.glossary#operation) Quantum que toma uno o más [qubits](xref:microsoft.quantum.glossary#qubit) como habilitadores para la operación de destino.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-126">A quantum [operation](xref:microsoft.quantum.glossary#operation) that takes one or more [qubits](xref:microsoft.quantum.glossary#qubit) as enablers for the target operation.</span></span> <span data-ttu-id="1e0d9-127">Para obtener más información, vea [operaciones de control y de datos contiguos](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-127">For more information, see [Controlled and adjoint operations](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="dirac-notation"></a><span data-ttu-id="1e0d9-128">Notación Dirac</span><span class="sxs-lookup"><span data-stu-id="1e0d9-128">Dirac Notation</span></span>

<span data-ttu-id="1e0d9-129">Una abreviatura simbólica que simplifica la representación de [los Estados de Quantum](xref:microsoft.quantum.glossary#quantum-state), también denominada notación *bra-les* .</span><span class="sxs-lookup"><span data-stu-id="1e0d9-129">A symbolic shorthand that simplifies the representation of [quantum states](xref:microsoft.quantum.glossary#quantum-state), also called *bra-ket* notation.</span></span>  <span data-ttu-id="1e0d9-130">La parte *Bra* representa un vector de fila, por ejemplo $ \bra{A } = \begin{ bmatrix } a {_ 1 } & a {_2 } \end{ bmatrix } $ y la parte *les* representa un vector de columna, $ \ket{B } = \begin{ bmatrix } b {_ 1 } \\ \\ b {_2 } \end{ bmatrix } $.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-130">The *bra* portion represents a row vector, for example  $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ and the *ket* portion represents a column vector, $\ket{B} = \begin{bmatrix} B{_1} \\\\ B{_2} \end{bmatrix}$.</span></span> <span data-ttu-id="1e0d9-131">Para obtener más información, consulte [notación Dirac](xref:microsoft.quantum.concepts.dirac).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-131">For more information, see [Dirac Notation](xref:microsoft.quantum.concepts.dirac).</span></span>

## <a name="eigenvalue"></a><span data-ttu-id="1e0d9-132">Eigenvalue</span><span class="sxs-lookup"><span data-stu-id="1e0d9-132">Eigenvalue</span></span>

<span data-ttu-id="1e0d9-133">Factor por el que la aplicación de la transformación cambia el tamaño de una [Eigenvector](xref:microsoft.quantum.glossary#eigenvector) de una transformación determinada.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-133">The factor by which the magnitude of an [eigenvector](xref:microsoft.quantum.glossary#eigenvector) of a given transformation is changed by the application of the transformation.</span></span>  <span data-ttu-id="1e0d9-134">Dada una matriz cuadrada $M $ y una $v Eigenvector $ , $MV = CV $ , donde $c $ es el eigenvalue y puede ser un número complejo de cualquier argumento.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-134">Given a square matrix $M$ and an eigenvector $v$, then $Mv = cv$, where $c$ is the eigenvalue and can be a complex number of any argument.</span></span> <span data-ttu-id="1e0d9-135">Para obtener más información, vea [conceptos de matriz avanzada](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-135">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="eigenvector"></a><span data-ttu-id="1e0d9-136">Eigenvector</span><span class="sxs-lookup"><span data-stu-id="1e0d9-136">Eigenvector</span></span>

<span data-ttu-id="1e0d9-137">Vector cuya dirección no cambia en una transformación determinada y cuya magnitud cambia por un factor que corresponde a [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)de ese vector.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-137">A vector whose direction is unchanged by a given transformation and whose magnitude is changed by a factor corresponding to that vector's [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue).</span></span> <span data-ttu-id="1e0d9-138">Dada una matriz cuadrada $M $ y una $c eigenvalue $ , $MV = CV $ , donde $v $ es un Eigenvector de la matriz y puede ser un número complejo de cualquier argumento.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-138">Given a square matrix $M$ and an eigenvalue $c$, then $Mv = cv$, where $v$ is an eigenvector of the matrix and can be a complex number of any argument.</span></span> <span data-ttu-id="1e0d9-139">Para obtener más información, vea [conceptos de matriz avanzada](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-139">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="entanglement"></a><span data-ttu-id="1e0d9-140">Entrelazamiento</span><span class="sxs-lookup"><span data-stu-id="1e0d9-140">Entanglement</span></span>

<span data-ttu-id="1e0d9-141">Las partículas Quantum, como [qubits](xref:microsoft.quantum.glossary#qubit), pueden estar conectadas o *desenredadas* de modo que no se puedan describir de forma independiente entre sí.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-141">Quantum particles, such as [qubits](xref:microsoft.quantum.glossary#qubit), can be connected or *entangled* such that they cannot be described independently from each other.</span></span> <span data-ttu-id="1e0d9-142">Los resultados de la medición se correlacionan incluso cuando se separan infinitamente.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-142">Their measurement results are correlated even when they are separated infinitely far away.</span></span> <span data-ttu-id="1e0d9-143">La inenredo es esencial para [medir](xref:microsoft.quantum.glossary#measurement) el [Estado](xref:microsoft.quantum.glossary#quantum-state) de un qubit.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-143">Entanglement is essential to [measuring](xref:microsoft.quantum.glossary#measurement) the [state](xref:microsoft.quantum.glossary#quantum-state) of a qubit.</span></span>  <span data-ttu-id="1e0d9-144">Para obtener más información, vea [conceptos de matriz avanzada](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-144">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="epr-pair"></a><span data-ttu-id="1e0d9-145">Par de EPR</span><span class="sxs-lookup"><span data-stu-id="1e0d9-145">EPR pair</span></span>

<span data-ttu-id="1e0d9-146">Uno de los cuatro Estados de Quantum con un [Estado](xref:microsoft.quantum.glossary#quantum-state) máximo de dos [qubits](xref:microsoft.quantum.glossary#qubit).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-146">One of four specific maximally entangled [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two [qubits](xref:microsoft.quantum.glossary#qubit).</span></span> <span data-ttu-id="1e0d9-147">Los cuatro Estados se definen como $ \ket { \ beta_ {ij } } = (\Mathbb{1 } \Otimes X ^ iz ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-147">The four states are defined $\ket{\beta_{ij}} = (\mathbb{1} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="1e0d9-148">Un par de EPR también se conoce como [Estado de campana](xref:microsoft.quantum.glossary#bell-state)</span><span class="sxs-lookup"><span data-stu-id="1e0d9-148">An EPR pair is also known as a [Bell state](xref:microsoft.quantum.glossary#bell-state)</span></span>

## <a name="evolution"></a><span data-ttu-id="1e0d9-149">Calidad</span><span class="sxs-lookup"><span data-stu-id="1e0d9-149">Evolution</span></span>

<span data-ttu-id="1e0d9-150">Cómo cambia el estado de un [Quantum](xref:microsoft.quantum.glossary#quantum-state) con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-150">How a [quantum state](xref:microsoft.quantum.glossary#quantum-state) changes over time.</span></span> <span data-ttu-id="1e0d9-151">Para obtener más información, consulte la [matriz exponencial](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-151">For more information, see [Matrix exponentials](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span></span>

## <a name="function"></a><span data-ttu-id="1e0d9-152">Función</span><span class="sxs-lookup"><span data-stu-id="1e0d9-152">Function</span></span>
<span data-ttu-id="1e0d9-153">Tipo de subrutina en el lenguaje de preguntas y respuestas puramente clásica (no Quantum).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-153">A type of subroutine in the Q# language that is purely classical (non-quantum).</span></span> <span data-ttu-id="1e0d9-154">Mientras que las funciones se usan en los algoritmos Quantum, no pueden actuar en [las operaciones](xref:microsoft.quantum.glossary#operation) [qubits](xref:microsoft.quantum.glossary#qubit) o Call.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-154">While functions are used within quantum algorithms, they cannot act on [qubits](xref:microsoft.quantum.glossary#qubit) or call [operations](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="1e0d9-155">Para obtener más información, vea [operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-155">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="gate"></a><span data-ttu-id="1e0d9-156">Canaliza</span><span class="sxs-lookup"><span data-stu-id="1e0d9-156">Gate</span></span>

<span data-ttu-id="1e0d9-157">Un término heredado para una [operación](xref:microsoft.quantum.glossary#operation)Quantum, basado en el concepto de las puertas lógicas clásicas.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-157">A legacy term for a quantum [operation](xref:microsoft.quantum.glossary#operation), based on the concept of classical logic gates.</span></span> <span data-ttu-id="1e0d9-158">Un [circuito Quantum](xref:microsoft.quantum.glossary#quantum-circuit-diagram) es una red de puertas (u operaciones), basada en el concepto similar de los circuitos lógicos de lógica.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-158">A [quantum circuit](xref:microsoft.quantum.glossary#quantum-circuit-diagram) is a network of gates (or operations), based on the similar concept of classical logic circuits.</span></span>

## <a name="global-phase"></a><span data-ttu-id="1e0d9-159">Fase global</span><span class="sxs-lookup"><span data-stu-id="1e0d9-159">Global phase</span></span>

<span data-ttu-id="1e0d9-160">Cuando dos [Estados](xref:microsoft.quantum.glossary#quantum-state) son idénticos a un múltiplo de un número complejo $e ^ {i \phi } $, se dice que se diferencian en una fase global.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-160">When two [states](xref:microsoft.quantum.glossary#quantum-state) are identical up to a multiple of a complex number $e^{i\phi}$, they are said to differ up to a global phase.</span></span> <span data-ttu-id="1e0d9-161">A diferencia de las fases locales, las fases globales no se pueden observar a través de cualquier [measurment](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-161">Unlike local phases, global phases cannot be observed through any [measurment](xref:microsoft.quantum.glossary#measurement).</span></span> <span data-ttu-id="1e0d9-162">Para obtener más información, consulte [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-162">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="hadamard"></a><span data-ttu-id="1e0d9-163">Hadamard</span><span class="sxs-lookup"><span data-stu-id="1e0d9-163">Hadamard</span></span>

<span data-ttu-id="1e0d9-164">La operación Hadamard (a la que también se hace referencia como la puerta Hadamard o la transformación) actúa en una sola [qubit](xref:microsoft.quantum.glossary#qubit) y la coloca en una [superposición](xref:microsoft.quantum.glossary#superposition) uniforme de $ \ket{0 } $ o $ \ket{1 } $ si el qubit está inicialmente en el estado $ \ket{0 } $.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-164">The Hadamard operation (also referred to as the Hadamard gate or transform) acts on a single [qubit](xref:microsoft.quantum.glossary#qubit) and puts it in an even [superposition](xref:microsoft.quantum.glossary#superposition) of $\ket{0}$ or $\ket{1}$ if the qubit is initially in the $\ket{0}$ state.</span></span> <span data-ttu-id="1e0d9-165">En Q #, esta operación se aplica mediante la operación predefinida [`H`](xref:microsoft.quantum.intrinsic.h) .</span><span class="sxs-lookup"><span data-stu-id="1e0d9-165">In Q#, this operation is applied by the pre-defined [`H`](xref:microsoft.quantum.intrinsic.h) operation.</span></span>

## <a name="immutable"></a><span data-ttu-id="1e0d9-166">Inmutable</span><span class="sxs-lookup"><span data-stu-id="1e0d9-166">Immutable</span></span>

<span data-ttu-id="1e0d9-167">Variable cuyo valor no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-167">A variable whose value cannot be changed.</span></span> <span data-ttu-id="1e0d9-168">Una variable inmutable en Q # se crea con la `let` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-168">An immutable variable in Q# is created using the `let` keyword.</span></span> <span data-ttu-id="1e0d9-169">Para declarar las variables que se *pueden* cambiar, use la palabra clave [mutable](xref:microsoft.quantum.glossary#immutable) para declarar y la `set` palabra clave para modificar el valor.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-169">To declare variables that *can* be changed, use the [mutable](xref:microsoft.quantum.glossary#immutable) keyword to declare and the `set` keyword to modify the value.</span></span> 

## <a name="measurement"></a><span data-ttu-id="1e0d9-170">Medición</span><span class="sxs-lookup"><span data-stu-id="1e0d9-170">Measurement</span></span>

<span data-ttu-id="1e0d9-171">Una manipulación de un [qubit](xref:microsoft.quantum.glossary#qubit) (o un conjunto de qubits) que produce el resultado de una observación, en efecto obtener un bit clásico.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-171">A manipulation of a [qubit](xref:microsoft.quantum.glossary#qubit) (or set of qubits) that yields the result of an observation, in effect obtaining a classical bit.</span></span> <span data-ttu-id="1e0d9-172">Para obtener más información, consulte [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-172">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span></span>

## <a name="mutable"></a><span data-ttu-id="1e0d9-173">Mutable</span><span class="sxs-lookup"><span data-stu-id="1e0d9-173">Mutable</span></span>

<span data-ttu-id="1e0d9-174">Variable cuyo valor se puede cambiar una vez creado.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-174">A variable whose value may be changed after it is created.</span></span> <span data-ttu-id="1e0d9-175">Una variable mutable en Q # se declara mediante la `mutable` palabra clave y se modifica mediante la `set` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-175">A mutable variable in Q# is declared using the `mutable` keyword and modified using the `set` keyword.</span></span> <span data-ttu-id="1e0d9-176">Las variables creadas con la `let` palabra clave son [inmutables](xref:microsoft.quantum.glossary#immutable) y su valor no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-176">Variables created with the `let` keyword are [immutable](xref:microsoft.quantum.glossary#immutable) and their value cannot be changed.</span></span>

## <a name="namespace"></a><span data-ttu-id="1e0d9-177">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1e0d9-177">Namespace</span></span>

<span data-ttu-id="1e0d9-178">Etiqueta para una colección de nombres relacionados (es decir, [operaciones](xref:microsoft.quantum.glossary#operation), [funciones](xref:microsoft.quantum.glossary#function)y [tipos definidos por el usuario](xref:microsoft.quantum.glossary#user-defined-type)).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-178">A label for a collection of related names (i.e., [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function), and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type)).</span></span> <span data-ttu-id="1e0d9-179">Por ejemplo, el espacio de nombres [Microsoft. Quantum. preparación](xref:microsoft.quantum.preparation) etiqueta todos los símbolos definidos en la biblioteca estándar que ayudan a preparar los Estados iniciales.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-179">For instance the namespace [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) labels all of the symbols defined in the standard library that help with preparing initial states.</span></span>

## <a name="operation"></a><span data-ttu-id="1e0d9-180">Operación</span><span class="sxs-lookup"><span data-stu-id="1e0d9-180">Operation</span></span>

<span data-ttu-id="1e0d9-181">La unidad básica de ejecución de Quantum en Q #.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-181">The basic unit of quantum execution in Q#.</span></span> <span data-ttu-id="1e0d9-182">Es aproximadamente equivalente a una función de C, C++ o Python, o a un método estático en C# o Java.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-182">It is roughly equivalent to a function in C, C++ or Python, or a static method in C# or Java.</span></span> <span data-ttu-id="1e0d9-183">Para obtener más información, vea [operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-183">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="operator-application"></a><span data-ttu-id="1e0d9-184">Operador Application</span><span class="sxs-lookup"><span data-stu-id="1e0d9-184">Operator application</span></span>

<span data-ttu-id="1e0d9-185">Realización de una operación Quantum.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-185">Performing a quantum operation.</span></span> <span data-ttu-id="1e0d9-186">Normalmente, esto aplica una matriz de unitarios al vector de estado de Quantum actual.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-186">This typically applies a unitary matrix to the current quantum state vector.</span></span>

## <a name="oracle"></a><span data-ttu-id="1e0d9-187">Oracle</span><span class="sxs-lookup"><span data-stu-id="1e0d9-187">Oracle</span></span>

<span data-ttu-id="1e0d9-188">Subrutina que proporciona información dependiente de datos a un algoritmo Quantum en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-188">A subroutine that provides data-dependent information to a quantum algorithm at runtime.</span></span> <span data-ttu-id="1e0d9-189">Normalmente, el objetivo es proporcionar una [superposición](xref:microsoft.quantum.glossary#superposition) de salidas que corresponden a las entradas que están en posición de superposición.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-189">Typically, the goal is to provide a [superposition](xref:microsoft.quantum.glossary#superposition) of outputs corresponding to inputs that are in superposition.</span></span> <span data-ttu-id="1e0d9-190">Para obtener más información, vea [Oracle](xref:microsoft.quantum.libraries.data-structures#oracles).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-190">For more information, see [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).</span></span>

## <a name="partial-application"></a><span data-ttu-id="1e0d9-191">Aplicación parcial</span><span class="sxs-lookup"><span data-stu-id="1e0d9-191">Partial application</span></span>

<span data-ttu-id="1e0d9-192">Llamar a una [función](xref:microsoft.quantum.glossary#function) u [operación](xref:microsoft.quantum.glossary#operation) sin todas las entradas necesarias.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-192">Calling a [function](xref:microsoft.quantum.glossary#function) or [operation](xref:microsoft.quantum.glossary#operation) without all the required inputs.</span></span> <span data-ttu-id="1e0d9-193">Esto devuelve un nuevo [llamador](xref:microsoft.quantum.glossary#callable) que solo necesita los parámetros que faltan (indicados por un carácter de subrayado) para que se proporcionen durante una aplicación futura.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-193">This returns a new [callable](xref:microsoft.quantum.glossary#callable) that only needs the missing parameters (indicated by an underscore) to be supplied during a future application.</span></span> <span data-ttu-id="1e0d9-194">Por ejemplo, dada la función, `MyFunc(x : int, y : int) : int {return x + y;}` se puede aplicar parcialmente a una nueva función `let NewFunc = MyFunc(_, 3)` .</span><span class="sxs-lookup"><span data-stu-id="1e0d9-194">For example, given the function `MyFunc(x : int, y : int) : int {return x + y;}` you can partially apply it to a new function `let NewFunc = MyFunc(_, 3)`.</span></span> <span data-ttu-id="1e0d9-195">Después, puede llamar a la nueva función más adelante con el parámetro que falta, `NewFunc(2)` que devuelve el valor *5*.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-195">You can then call the new function at a later time with the missing parameter `NewFunc(2)` which returns the value *5*.</span></span>  <span data-ttu-id="1e0d9-196">Para obtener más información, vea [aplicación parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-196">For more information, see [Partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span></span>

## <a name="pauli-operators"></a><span data-ttu-id="1e0d9-197">Operadores Pauli</span><span class="sxs-lookup"><span data-stu-id="1e0d9-197">Pauli operators</span></span>

<span data-ttu-id="1e0d9-198">Un conjunto de tres matrices unitarios de 2 x 2 conocidas como las `X` `Y` operaciones, y `Z` Quantum.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-198">A set of three 2 x 2 unitary matrices known as the `X`, `Y` and `Z` quantum operations.</span></span> <span data-ttu-id="1e0d9-199">La matriz de identidad, $I $ , suele incluirse también en el conjunto.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-199">The identity matrix, $I$, is often included in the set as well.</span></span>  <span data-ttu-id="1e0d9-200">$I = \begin{ bmatrix } 1 & 0 \\ \\ 0 & 1 \end{ bmatrix } $, $X = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } $, $Y = \begin{ bmatrix } 0 &-i \\ \\ & 0 \end{ bmatrix } $, $Z = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } $.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-200">$I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix}$, $X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}$.</span></span>   <span data-ttu-id="1e0d9-201">Para obtener más información, consulte [operaciones de un solo qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-201">For more information, see [Single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>

## <a name="quantum-circuit-diagram"></a><span data-ttu-id="1e0d9-202">Diagrama del circuito de Quantum</span><span class="sxs-lookup"><span data-stu-id="1e0d9-202">Quantum circuit diagram</span></span>

<span data-ttu-id="1e0d9-203">Un método para representar gráficamente la secuencia de [operaciones](xref:microsoft.quantum.glossary#operation) (o [puertas](xref:microsoft.quantum.glossary#gate)) para programas Quantum simples, por ejemplo</span><span class="sxs-lookup"><span data-stu-id="1e0d9-203">A method to graphically represent the sequence of [operations](xref:microsoft.quantum.glossary#operation) (or [gates](xref:microsoft.quantum.glossary#gate)) for simple quantum programs, for example</span></span> 

![Diagrama de circuitos de ejemplo](~/media/qpe.png)<span data-ttu-id="1e0d9-205">.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-205">.</span></span> 

<span data-ttu-id="1e0d9-206">Para obtener más información, consulte los [circuitos de Quantum](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-206">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits).</span></span>

## <a name="quantum-libraries"></a><span data-ttu-id="1e0d9-207">Bibliotecas de Quantum</span><span class="sxs-lookup"><span data-stu-id="1e0d9-207">Quantum libraries</span></span>

<span data-ttu-id="1e0d9-208">Colecciones de [operaciones](xref:microsoft.quantum.glossary#operation), [funciones](xref:microsoft.quantum.glossary#function) y [tipos definidos por el usuario](xref:microsoft.quantum.glossary#user-defined-type) para crear programas de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-208">Collections of [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) for creating Q# programs.</span></span> <span data-ttu-id="1e0d9-209">La [biblioteca estándar](xref:microsoft.quantum.libraries.standard.intro) se instala de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-209">The [Standard library](xref:microsoft.quantum.libraries.standard.intro) is installed by default.</span></span> <span data-ttu-id="1e0d9-210">Otras bibliotecas disponibles son la biblioteca de [química](xref:microsoft.quantum.chemistry.concepts.intro), la [biblioteca de valores numéricos](xref:microsoft.quantum.numerics.intro) y la biblioteca de [machine learning](xref:microsoft.quantum.machine-learning.concepts.intro).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-210">Other libraries available are the [Chemistry library](xref:microsoft.quantum.chemistry.concepts.intro), the [Numerics library](xref:microsoft.quantum.numerics.intro) and the [Machine learning library](xref:microsoft.quantum.machine-learning.concepts.intro).</span></span>

## <a name="quantum-state"></a><span data-ttu-id="1e0d9-211">Estado de Quantum</span><span class="sxs-lookup"><span data-stu-id="1e0d9-211">Quantum state</span></span>

<span data-ttu-id="1e0d9-212">Estado preciso de un sistema de Quantum aislado, del que se pueden extraer las probabilidades de [medición](xref:microsoft.quantum.glossary#measurement) .</span><span class="sxs-lookup"><span data-stu-id="1e0d9-212">The precise state of an isolated quantum system, from which [measurement](xref:microsoft.quantum.glossary#measurement) probabilities can be extracted.</span></span> <span data-ttu-id="1e0d9-213">En Quantum Computing, el simulador de Quantum usa esta información para simular el modo en que qubits responde a las operaciones.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-213">In quantum computing, the quantum simulator uses this information to simulate how qubits respond to operations.</span></span> <span data-ttu-id="1e0d9-214">Para obtener más información, consulte [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-214">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="qubit"></a><span data-ttu-id="1e0d9-215">Qubit</span><span class="sxs-lookup"><span data-stu-id="1e0d9-215">Qubit</span></span>

<span data-ttu-id="1e0d9-216">Unidad básica de información de Quantum, análoga a un *bit* de la informática clásica.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-216">A basic unit of quantum information, analogous to a *bit* in classical computing.</span></span> <span data-ttu-id="1e0d9-217">Para obtener más información, consulte [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-217">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="repeat-until-success"></a><span data-ttu-id="1e0d9-218">Repetir hasta éxito</span><span class="sxs-lookup"><span data-stu-id="1e0d9-218">Repeat-until-success</span></span>

<span data-ttu-id="1e0d9-219">Un algoritmo Quantum que se ejecuta con probabilidad de éxito.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-219">A quantum algorithm that probabilistically succeeds.</span></span> <span data-ttu-id="1e0d9-220">En caso de error, la rutina volverá a intentarlo hasta que sea correcta (o se alcance un límite).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-220">Upon failure, the routine will retry until successful (or a limit has been reached).</span></span> <span data-ttu-id="1e0d9-221">Para obtener más información, consulte [repetir hasta éxito (RU)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) .</span><span class="sxs-lookup"><span data-stu-id="1e0d9-221">For more information, see [Repeat Until Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span></span>

## <a name="standard-libraries"></a><span data-ttu-id="1e0d9-222">Bibliotecas estándar</span><span class="sxs-lookup"><span data-stu-id="1e0d9-222">Standard libraries</span></span>

<span data-ttu-id="1e0d9-223">[Operaciones](xref:microsoft.quantum.glossary#operation), [funciones](xref:microsoft.quantum.glossary#function) y [tipos definidos por el usuario](xref:microsoft.quantum.glossary#user-defined-type) que se instalan junto con el compilador de Q # durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-223">[Operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) that are installed along with the Q# compiler during installation.</span></span> <span data-ttu-id="1e0d9-224">La implementación de la biblioteca estándar es independiente con respecto a los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-224">The standard library implementation is agnostic with respect to target machines.</span></span> <span data-ttu-id="1e0d9-225">Para obtener más información, vea [bibliotecas estándar](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-225">For more information, see [Standard libraries](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="superposition"></a><span data-ttu-id="1e0d9-226">Superposición</span><span class="sxs-lookup"><span data-stu-id="1e0d9-226">Superposition</span></span>

<span data-ttu-id="1e0d9-227">El concepto de Quantum Computing que [qubit](xref:microsoft.quantum.glossary#qubit) es una combinación lineal de dos Estados, $ \ket{0 } $ y $ \ket{1 } $, hasta que se [mida](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-227">The concept in quantum computing that a [qubit](xref:microsoft.quantum.glossary#qubit) is a linear combination of two states, $\ket{0}$ and $\ket{1}$, until it is [measured](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="1e0d9-228">Para obtener más información, vea Descripción de la [informática Quantum](xref:microsoft.quantum.overview.understanding).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-228">For more information, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding).</span></span>

## <a name="target-machine"></a><span data-ttu-id="1e0d9-229">Máquina de destino</span><span class="sxs-lookup"><span data-stu-id="1e0d9-229">Target machine</span></span>

<span data-ttu-id="1e0d9-230">Un destino de compilación que reduce un programa Quantum abstracto hacia el hardware o la simulación.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-230">A compilation target that lowers an abstract quantum program towards hardware or simulation.</span></span> <span data-ttu-id="1e0d9-231">Esto suele incluir reescrituras para muchos propósitos, incluidos el reemplazo de la puerta, la codificación para la corrección de errores, el diseño geométrico y otros.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-231">This typically include re-writes for many purposes including gate replacement, encoding for error correction, geometric layout and others.</span></span> <span data-ttu-id="1e0d9-232">Para obtener más información, consulte [simuladores Quantum y aplicaciones host](xref:microsoft.quantum.machines).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-232">For more information, see [Quantum simulators and host applications](xref:microsoft.quantum.machines).</span></span>

## <a name="teleportation"></a><span data-ttu-id="1e0d9-233">Teleportabilidad</span><span class="sxs-lookup"><span data-stu-id="1e0d9-233">Teleportation</span></span>

<span data-ttu-id="1e0d9-234">Un método para volver a generar los datos, o el [Estado de Quantum](xref:microsoft.quantum.glossary#quantum-state), de un [qubit](xref:microsoft.quantum.glossary#qubit) de un lugar a otro sin mover físicamente el qubit, con el [inenredo](xref:microsoft.quantum.glossary#entanglement) y la [medición](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-234">A method for regenerating data, or the [quantum state](xref:microsoft.quantum.glossary#quantum-state), of one [qubit](xref:microsoft.quantum.glossary#qubit) from one place to another without physically moving the qubit, using [entanglement](xref:microsoft.quantum.glossary#entanglement) and [measurement](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="1e0d9-235">Para obtener más información, consulte los [circuitos Quantum](xref:microsoft.quantum.concepts.circuits) y los Kata respectivos en [Quantum katas](xref:microsoft.quantum.overview.katas).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-235">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits) and the respective kata at [Quantum Katas](xref:microsoft.quantum.overview.katas).</span></span>

## <a name="tuple"></a><span data-ttu-id="1e0d9-236">Tuple</span><span class="sxs-lookup"><span data-stu-id="1e0d9-236">Tuple</span></span>

<span data-ttu-id="1e0d9-237">Colección de valores separados por comas que actúa como un valor único.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-237">A collection of comma-separated values that acts as a single value.</span></span> <span data-ttu-id="1e0d9-238">El *tipo* de una tupla se define mediante los tipos de valores que contiene.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-238">The *type* of a tuple is defined by the types of values it contains.</span></span> <span data-ttu-id="1e0d9-239">En Q #, las tuplas son [inmutables](xref:microsoft.quantum.glossary#immutable) y se pueden anidar, contener matrices o usar en una matriz.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-239">In Q#, tuples are [immutable](xref:microsoft.quantum.glossary#immutable) and can be nested, contain arrays, or used in an array.</span></span> <span data-ttu-id="1e0d9-240">Para obtener más información, vea [tipos de tupla](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-240">For more information, see [Tuple types](xref:microsoft.quantum.guide.types#tuple-types).</span></span>

## <a name="unitary-operator"></a><span data-ttu-id="1e0d9-241">Operador unitario</span><span class="sxs-lookup"><span data-stu-id="1e0d9-241">Unitary operator</span></span>

<span data-ttu-id="1e0d9-242">Un operador cuyo inverso es igual a su signo [contiguo](xref:microsoft.quantum.glossary#adjoint), es decir, $UU ^ {\dagger } = \id $ .</span><span class="sxs-lookup"><span data-stu-id="1e0d9-242">An operator whose inverse is equal to its [adjoint](xref:microsoft.quantum.glossary#adjoint), i.e., $UU^{\dagger} = \id$.</span></span>

## <a name="user-defined-type"></a><span data-ttu-id="1e0d9-243">Tipo definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="1e0d9-243">User-defined type</span></span>

<span data-ttu-id="1e0d9-244">Colección de tipos integrados o definidos previamente que se pueden denominar una sola unidad.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-244">A collection of built-in or previously defined types that may be referred to as a single unit.</span></span> <span data-ttu-id="1e0d9-245">Para obtener más información, vea [tipos definidos por el usuario](xref:microsoft.quantum.guide.types#user-defined-types).</span><span class="sxs-lookup"><span data-stu-id="1e0d9-245">For more information, see [User-defined types](xref:microsoft.quantum.guide.types#user-defined-types).</span></span>