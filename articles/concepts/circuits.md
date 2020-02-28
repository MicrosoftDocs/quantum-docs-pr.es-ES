---
title: Circuitos cuánticos
description: Obtenga información sobre cómo representar visualmente operaciones Quantum simples y complejas con diagramas de circuito de Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 8ba4648f1837065d15957a01ab4ca8dd2d490a42
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905155"
---
# <a name="quantum-circuits"></a><span data-ttu-id="f068d-103">Circuitos Quantum</span><span class="sxs-lookup"><span data-stu-id="f068d-103">Quantum Circuits</span></span>
<span data-ttu-id="f068d-104">Considere, por un momento, la transformación unitario $ \text{CNOT} _{01}(H\otimes 1) $.</span><span class="sxs-lookup"><span data-stu-id="f068d-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="f068d-105">Esta secuencia de la puerta es de importancia fundamental para la informática de Quantum, ya que crea un estado de dos qubit con el máximo de supuestos:</span><span class="sxs-lookup"><span data-stu-id="f068d-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="f068d-106">$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $</span><span class="sxs-lookup"><span data-stu-id="f068d-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="f068d-107">Las operaciones con esta complejidad o mayor son ubicuas en los algoritmos Quantum y la corrección de errores Quantum, por lo que debe ser una buena forma de que hay un método simple para su visualización denominado *Diagrama de circuito Quantum*.</span><span class="sxs-lookup"><span data-stu-id="f068d-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="f068d-108">El diagrama del circuito para preparar este estado de Quantum con el máximo grado de enredo es:</span><span class="sxs-lookup"><span data-stu-id="f068d-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f068d-109">![diagrama de circuito para un estado de dos qubits con un máximo de dos](~/media/Concepts1.png)</span><span class="sxs-lookup"><span data-stu-id="f068d-109">![Circuit diagram for a maximally entangled two-qubit state](~/media/Concepts1.png)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="f068d-110">Convenciones de diagrama del circuito de Quantum</span><span class="sxs-lookup"><span data-stu-id="f068d-110">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="f068d-111">Este lenguaje visual para las operaciones Quantum puede ser más fácil de entender que escribir su matriz equivalente una vez que comprenda las convenciones para expresar un circuito de Quantum.</span><span class="sxs-lookup"><span data-stu-id="f068d-111">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="f068d-112">Revisaremos estas convenciones a continuación.</span><span class="sxs-lookup"><span data-stu-id="f068d-112">We review these conventions below.</span></span>

<span data-ttu-id="f068d-113">En un diagrama de circuitos, cada línea sólida muestra un qubit o, en general, un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="f068d-113">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="f068d-114">Por Convención, la línea superior es qubit Register $0 $ y el resto se etiqueta secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="f068d-114">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="f068d-115">El circuito de ejemplo anterior se representa como si actuara en dos qubits (o equivalentes en dos registros que se componen de un qubit).</span><span class="sxs-lookup"><span data-stu-id="f068d-115">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="f068d-116">Las puertas que actúan en uno o varios registros de qubit se indican como un cuadro.</span><span class="sxs-lookup"><span data-stu-id="f068d-116">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="f068d-117">Por ejemplo, el símbolo</span><span class="sxs-lookup"><span data-stu-id="f068d-117">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f068d-118">![símbolo para una operación de Hadamard que actúa en un registro de qubit único](~/media/concepts_2.png)</span><span class="sxs-lookup"><span data-stu-id="f068d-118">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/concepts_2.png)</span></span>

<span data-ttu-id="f068d-119">es una operación de [Hadamard](xref:microsoft.quantum.intrinsic.h) que actúa en un registro de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="f068d-119">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="f068d-120">Las puertas de Quantum se ordenan cronológicamente con la puerta situada más a la izquierda como la puerta que se aplica primero a qubits.</span><span class="sxs-lookup"><span data-stu-id="f068d-120">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="f068d-121">En otras palabras, si se imagen de los cables como que contienen el estado de Quantum, los cables llevan el estado de Quantum a través de cada una de las puertas del diagrama de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="f068d-121">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="f068d-122">Es decir</span><span class="sxs-lookup"><span data-stu-id="f068d-122">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f068d-123">![diagrama de las puertas Quantum que se aplican](~/media/concepts_3.png) de izquierda a derecha</span><span class="sxs-lookup"><span data-stu-id="f068d-123">![Diagram of quantum gates being applied left-to-right](~/media/concepts_3.png)</span></span>

<span data-ttu-id="f068d-124">es la matriz unitario $CBA $.</span><span class="sxs-lookup"><span data-stu-id="f068d-124">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="f068d-125">La multiplicación de matrices obedece la Convención opuesta: primero se aplica la matriz que se encuentra más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="f068d-125">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="f068d-126">Sin embargo, en los diagramas de circuito Quantum, se aplica primero la puerta situada más a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="f068d-126">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="f068d-127">En ocasiones, esta diferencia puede llevar a confusión, por lo que es importante tener en cuenta esta diferencia significativa entre los diagramas de la notación algebraico lineal y del circuito de Quantum.</span><span class="sxs-lookup"><span data-stu-id="f068d-127">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="f068d-128">Entradas y salidas de los circuitos Quantum</span><span class="sxs-lookup"><span data-stu-id="f068d-128">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="f068d-129">Todos los ejemplos anteriores han tenido exactamente el mismo número de entradas de cables (qubits) en una puerta de Quantum como el número de cables de la puerta de Quantum.</span><span class="sxs-lookup"><span data-stu-id="f068d-129">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="f068d-130">En primer lugar, es posible que parezca razonable que los circuitos Quantum pudieran tener más salidas que las entradas en general.</span><span class="sxs-lookup"><span data-stu-id="f068d-130">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="f068d-131">Sin embargo, esto no es posible, ya que todas las operaciones de Quantum, la medida de guardado, son unitarios y, por tanto, reversibles.</span><span class="sxs-lookup"><span data-stu-id="f068d-131">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="f068d-132">Si no tenían el mismo número de salidas que las entradas, no serían reversibles y, por lo tanto, no serían una contradicción.</span><span class="sxs-lookup"><span data-stu-id="f068d-132">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="f068d-133">Por esta razón, todos los cuadros dibujados en un diagrama de circuitos deben tener exactamente el mismo número de cables que lo señalan.</span><span class="sxs-lookup"><span data-stu-id="f068d-133">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="f068d-134">Los diagramas de circuitos de varios qubit siguen convenciones similares a las de qubit.</span><span class="sxs-lookup"><span data-stu-id="f068d-134">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="f068d-135">Como ejemplo de clarificación, podemos definir una operación unitario de dos qubit $B $ para que sea $ (H S\otimes X) $ y expresar el circuito de forma equivalente.</span><span class="sxs-lookup"><span data-stu-id="f068d-135">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f068d-136">![diagrama de circuito de una operación de unitario de dos qubit](~/media/concepts_4.png)</span><span class="sxs-lookup"><span data-stu-id="f068d-136">![Circuit diagram of a two-qubit unitary operation](~/media/concepts_4.png)</span></span>

<span data-ttu-id="f068d-137">También podemos ver $B $ como si tuvieran una acción en un solo registro de dos qubit, en lugar de en 2 1-qubit, según el contexto en el que se use el circuito.</span><span class="sxs-lookup"><span data-stu-id="f068d-137">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="f068d-138">Quizás la propiedad más útil de estos diagramas de circuitos abstractos es que permiten describir algoritmos Quantum complicados en un nivel alto sin tener que compilarlos en las puertas fundamentales.</span><span class="sxs-lookup"><span data-stu-id="f068d-138">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="f068d-139">Esto significa que puede obtener un Intuition sobre el flujo de datos para un algoritmo Quantum grande sin necesidad de comprender todos los detalles de cómo funciona cada una de las subrutinas dentro del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="f068d-139">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="f068d-140">Puertas controladas</span><span class="sxs-lookup"><span data-stu-id="f068d-140">Controlled gates</span></span>
<span data-ttu-id="f068d-141">La otra construcción que se integra en los diagramas del circuito de Quantum de varios qubit es control.</span><span class="sxs-lookup"><span data-stu-id="f068d-141">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="f068d-142">La acción de una puerta de Quantum controlada por una vez, indicada como $ \Lambda (G) $, donde un valor de qubit único controla la aplicación de $G $, se puede entender examinando el ejemplo siguiente de una entrada de estado de producto $ \Lambda (G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ PSI} $</span><span class="sxs-lookup"><span data-stu-id="f068d-142">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="f068d-143">Es decir, la barrera controlada aplica $G $ al registro que contiene $ \psi $ si y solo si el control qubit toma el valor $1 $.</span><span class="sxs-lookup"><span data-stu-id="f068d-143">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="f068d-144">En general, se describen las operaciones controladas en diagramas de circuitos como</span><span class="sxs-lookup"><span data-stu-id="f068d-144">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f068d-145">![diagrama de circuito de una puerta controlada por un](~/media/concepts_5.png)</span><span class="sxs-lookup"><span data-stu-id="f068d-145">![Circuit diagram of a singly controlled gate](~/media/concepts_5.png)</span></span>

<span data-ttu-id="f068d-146">Aquí el círculo negro denota el bit de Quantum en el que se controla la puerta y una conexión vertical denota la unitario que se aplica cuando el control qubit toma el valor $1 $.</span><span class="sxs-lookup"><span data-stu-id="f068d-146">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="f068d-147">Para los casos especiales en los que $G = X $ y $G = Z $, presentamos la siguiente notación para describir la versión controlada de las puertas (tenga en cuenta que la puerta controlada-X es la [$CNOT $ Gate](xref:microsoft.quantum.intrinsic.cnot)):</span><span class="sxs-lookup"><span data-stu-id="f068d-147">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f068d-148">![diagrama de circuito para casos especiales de puertas controladas](~/media/concepts_6.png)</span><span class="sxs-lookup"><span data-stu-id="f068d-148">![Circuit diagram for special cases of controlled gates](~/media/concepts_6.png)</span></span>

<span data-ttu-id="f068d-149">Q # proporciona métodos para generar automáticamente la versión controlada de una operación, lo que evita que el programador tenga que codificar estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="f068d-149">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="f068d-150">A continuación se muestra un ejemplo de esto:</span><span class="sxs-lookup"><span data-stu-id="f068d-150">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="f068d-151">Operador de medida</span><span class="sxs-lookup"><span data-stu-id="f068d-151">Measurement operator</span></span>
<span data-ttu-id="f068d-152">La operación restante para visualizar en diagramas de circuitos es la medida.</span><span class="sxs-lookup"><span data-stu-id="f068d-152">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="f068d-153">La medición toma un registro de qubit, lo mide y genera el resultado como información clásica.</span><span class="sxs-lookup"><span data-stu-id="f068d-153">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="f068d-154">Una operación de medición se denota mediante un símbolo de medidor y siempre toma como entrada un registro qubit (indicado por una línea sólida) y genera información clásica (se indica mediante una línea doble).</span><span class="sxs-lookup"><span data-stu-id="f068d-154">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="f068d-155">En concreto, este Subcircuito tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="f068d-155">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f068d-156">![símbolo que representa una operación de medición](~/media/concepts_7.png)</span><span class="sxs-lookup"><span data-stu-id="f068d-156">![Symbol representing a measurement operation](~/media/concepts_7.png)</span></span>

<span data-ttu-id="f068d-157">Q # implementa un [operador de medida](xref:microsoft.quantum.intrinsic.measure) para este fin.</span><span class="sxs-lookup"><span data-stu-id="f068d-157">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="f068d-158">Vea la [sección sobre medidas](xref:microsoft.quantum.libraries.standard.prelude#measurements) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f068d-158">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="f068d-159">Del mismo modo, el Subcircuito</span><span class="sxs-lookup"><span data-stu-id="f068d-159">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f068d-160">![diagrama del circuito que representa una operación controlada](~/media/concepts_8.png)</span><span class="sxs-lookup"><span data-stu-id="f068d-160">![Circuit diagram representing a controlled operation](~/media/concepts_8.png)</span></span>

<span data-ttu-id="f068d-161">proporciona una puerta controlada por clases, donde $G $ se aplica en el bit de control clásico que es el valor $1 $.</span><span class="sxs-lookup"><span data-stu-id="f068d-161">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="f068d-162">Diagrama del circuito de teleportabilidad</span><span class="sxs-lookup"><span data-stu-id="f068d-162">Teleportation circuit diagram</span></span>
<span data-ttu-id="f068d-163">La [teleportabilidad de Quantum](xref:microsoft.quantum.techniques.puttingittogether) es quizás el mejor algoritmo Quantum para ilustrar estos componentes.</span><span class="sxs-lookup"><span data-stu-id="f068d-163">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="f068d-164">La teleportabilidad de Quantum es un método para mover datos dentro de un equipo Quantum (o incluso entre equipos Quantum distantes en una red Quantum) mediante el uso de la inenredo y la medición.</span><span class="sxs-lookup"><span data-stu-id="f068d-164">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="f068d-165">Curiosamente, realmente es capaz de mover un estado de Quantum, por ejemplo, el valor de un qubit determinado, de un qubit a otro, sin tener que saber aún cuál es el valor de qubit.</span><span class="sxs-lookup"><span data-stu-id="f068d-165">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="f068d-166">Esto es necesario para que el protocolo funcione según las leyes de la mecánica de Quantum.</span><span class="sxs-lookup"><span data-stu-id="f068d-166">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="f068d-167">A continuación se proporciona el circuito de teleportabilidad de Quantum; También proporcionamos una versión anotada del circuito para ilustrar cómo leer el circuito de Quantum.</span><span class="sxs-lookup"><span data-stu-id="f068d-167">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
<span data-ttu-id="f068d-168">![circuito de teleportabilidad de Quantum](~/media/concepts_tp2.png)</span><span class="sxs-lookup"><span data-stu-id="f068d-168">![Quantum teleportation circuit](~/media/concepts_tp2.png)</span></span>
