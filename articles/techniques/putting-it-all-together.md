---
title: 'Técnicas de preguntas y respuestas: colocarlas todas juntas | Microsoft Docs'
description: 'Técnicas de Q #: reunir todo'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f65b3e260f98a7a90da13b62edd6cc63d200f5af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183274"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="0a5c4-103">Reunir todo: teleportabilidad</span><span class="sxs-lookup"><span data-stu-id="0a5c4-103">Putting it All Together: Teleportation</span></span> #
<span data-ttu-id="0a5c4-104">Volvamos al ejemplo del circuito de teleportabilidad definido en los circuitos de [Quantum](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="0a5c4-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="0a5c4-105">Vamos a usar esto para ilustrar los conceptos que hemos aprendido hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="0a5c4-106">A continuación se proporciona una explicación de la teleportabilidad de Quantum para quienes no están familiarizados con la teoría, seguidos de un tutorial de la implementación del código en Q #.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="0a5c4-107">Teleportabilidad de Quantum: teoría</span><span class="sxs-lookup"><span data-stu-id="0a5c4-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="0a5c4-108">La teleportabilidad de Quantum es una técnica para enviar un estado de Quantum desconocido (al que haremos referencia como "__mensaje__") desde una qubit en una ubicación a una qubit en otra ubicación (haremos referencia a estas qubits como "__aquí__" y "__allí__", respectivamente).</span><span class="sxs-lookup"><span data-stu-id="0a5c4-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="0a5c4-109">Podemos representar el __mensaje__ como un vector mediante la notación Dirac:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="0a5c4-110">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="0a5c4-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="0a5c4-111">Se desconoce el estado del qubit de __mensajes__ , ya que no se conocen los valores de $ \alpha $ y $ \beta $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="0a5c4-112">Paso 1: creación de un estado desenredado</span><span class="sxs-lookup"><span data-stu-id="0a5c4-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="0a5c4-113">Con el fin de enviar el __mensaje__ que necesitamos para que __el qubit se__ qubit __allí__.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="0a5c4-114">Esto se logra aplicando una puerta Hadamard, seguida de una puerta CNOT.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="0a5c4-115">Echemos un vistazo a las matemáticas detrás de estas operaciones de la puerta.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="0a5c4-116">Comenzaremos con qubits __aquí__ __y en__ el estado $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="0a5c4-117">Después de la inenredo de estos qubits, se encuentran en el estado:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="0a5c4-118">$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $</span><span class="sxs-lookup"><span data-stu-id="0a5c4-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="0a5c4-119">Paso 2: enviar el mensaje</span><span class="sxs-lookup"><span data-stu-id="0a5c4-119">Step 2: Send the message</span></span>
<span data-ttu-id="0a5c4-120">Para enviar el __mensaje__ , primero se aplica una puerta CNOT con el __mensaje__ qubit y __aquí__ qubit como entradas (el __mensaje__ qubit es el control y __aquí__ qubit es el qubit de destino, en esta instancia).</span><span class="sxs-lookup"><span data-stu-id="0a5c4-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="0a5c4-121">Este estado de entrada se puede escribir:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-121">This input state can be written:</span></span>

<span data-ttu-id="0a5c4-122">$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $</span><span class="sxs-lookup"><span data-stu-id="0a5c4-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="0a5c4-123">Se expande a:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-123">This expands to:</span></span>

<span data-ttu-id="0a5c4-124">$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $</span><span class="sxs-lookup"><span data-stu-id="0a5c4-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="0a5c4-125">Como recordatorio, la puerta CNOT voltea el qubit de destino cuando el qubit de control es 1.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="0a5c4-126">Por ejemplo, una entrada de $ \ket{000}$ no producirá ningún cambio, ya que el primer qubit (el control) es 0.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="0a5c4-127">Sin embargo, tome un caso en el que el primer qubit es 1, por ejemplo, una entrada de $ \ket{100}$.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="0a5c4-128">En esta instancia, la salida es $ \ket{110}$ como el segundo qubit (el destino) se voltea mediante la puerta CNOT.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="0a5c4-129">Ahora vamos a tener en cuenta la salida una vez que la puerta CNOT haya actuado en la entrada anterior.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="0a5c4-130">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-130">The result is:</span></span>

<span data-ttu-id="0a5c4-131">$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $</span><span class="sxs-lookup"><span data-stu-id="0a5c4-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="0a5c4-132">El siguiente paso para enviar el __mensaje__ consiste en aplicar una puerta Hadamard al __mensaje__ qubit (que es el primer qubit de cada término).</span><span class="sxs-lookup"><span data-stu-id="0a5c4-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="0a5c4-133">Como recordatorio, la puerta Hadamard hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="0a5c4-134">Entrada</span><span class="sxs-lookup"><span data-stu-id="0a5c4-134">Input</span></span> | <span data-ttu-id="0a5c4-135">Output</span><span class="sxs-lookup"><span data-stu-id="0a5c4-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="0a5c4-136">$ \ket{0}$</span><span class="sxs-lookup"><span data-stu-id="0a5c4-136">$\ket{0}$</span></span>  | <span data-ttu-id="0a5c4-137">$ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="0a5c4-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="0a5c4-138">$ \ket{1}$</span><span class="sxs-lookup"><span data-stu-id="0a5c4-138">$\ket{1}$</span></span>  | <span data-ttu-id="0a5c4-139">$ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="0a5c4-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="0a5c4-140">Si se aplica la puerta Hadamard al primer qubit de cada término de la salida anterior, obtenemos el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="0a5c4-141">$ $ \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{ \sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="0a5c4-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="0a5c4-142">Tenga en cuenta que cada término tiene $2 \frac{1}{\sqrt{2}} $ factores.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="0a5c4-143">Podemos multiplicarlos por el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="0a5c4-144">$ $ \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="0a5c4-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="0a5c4-145">$ \Frac{1}{2}$ factor es común a cada término, por lo que ahora podemos desecharlo fuera de los corchetes:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="0a5c4-146">$ $ \frac{1}{2}\big [\alpha (\ket{0} + \ket{1}) \ket{00} + \alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="0a5c4-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="0a5c4-147">A continuación, podemos multiplicar los corchetes por cada término:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="0a5c4-148">$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="0a5c4-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="0a5c4-149">Paso 3: medir el resultado</span><span class="sxs-lookup"><span data-stu-id="0a5c4-149">Step 3: Measure the result</span></span>

<span data-ttu-id="0a5c4-150">Debido a __la existencia de__ __aquí__ y, cualquier medida que se produzca __aquí__ afectará al estado de __allí__.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="0a5c4-151">Si medimos el primer y el segundo qubit (__mensaje__ y __aquí__) podemos obtener información sobre __el estado en__ el que se encuentra, debido a la propiedad de la inenredo.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="0a5c4-152">Si medimos y obtenemos el resultado 00, la superposición se contrae, lo que solo mantiene los términos coherentes con este resultado.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="0a5c4-153">Eso es $ \alpha\ket{000} + \beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="0a5c4-154">Esto se puede refactorizar a $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="0a5c4-155">Por lo tanto, si medimos el primer y el segundo qubit para que sea 00, sabemos que el tercer qubit, __ahí__, está en el estado $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="0a5c4-156">Si medimos y obtenemos el resultado 01, la superposición se contrae, lo que solo mantiene los términos coherentes con este resultado.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="0a5c4-157">Eso es $ \alpha\ket{011} + \beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="0a5c4-158">Esto se puede refactorizar a $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="0a5c4-159">Por lo tanto, si medimos el primer y el segundo qubit para que sea 01, sabemos que el tercer qubit, __ahí__, está en el estado $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="0a5c4-160">Si medimos y obtenemos el resultado 10, la superposición se contrae, lo que solo mantiene los términos coherentes con este resultado.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="0a5c4-161">Ese es $ \alpha\ket{100}-{101}\beta\ket $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="0a5c4-162">Esto se puede refactorizar a $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="0a5c4-163">Por lo tanto, si medimos el primer y el segundo qubit para que sea 10, sabemos que el tercer qubit, __ahí__, está en el estado $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="0a5c4-164">Si medimos y obtenemos el resultado 11, la superposición se contrae, lo que solo mantiene los términos coherentes con este resultado.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="0a5c4-165">Ese es $ \alpha\ket{111}-{110}\beta\ket $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="0a5c4-166">Esto se puede refactorizar a $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="0a5c4-167">Por lo tanto, si medimos el primer y el segundo qubit para que sea 11, sabemos que el tercer qubit, __ahí__, está en el estado $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="0a5c4-168">Paso 4: interpretar el resultado</span><span class="sxs-lookup"><span data-stu-id="0a5c4-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="0a5c4-169">Como recordatorio, el __mensaje__ original que quería enviar era:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="0a5c4-170">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="0a5c4-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="0a5c4-171">Necesitamos obtener la qubit en este estado, de modo __que el estado__ recibido sea el que se pretendía.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="0a5c4-172">Si medimos y obtuvieron el resultado __00, el tercer qubit, en__el estado $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="0a5c4-173">Como este es el __mensaje__previsto, no se requiere ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="0a5c4-174">Si medimos y obtuvieron el resultado __01, el tercer qubit, en__el estado $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="0a5c4-175">Esto difiere del __mensaje__previsto; sin embargo, si se aplica una puerta not, nos proporciona el estado deseado $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="0a5c4-176">Si medimos y obtuvieron un resultado de __10, el tercer qubit, en__el estado $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="0a5c4-177">Esto difiere del __mensaje__previsto; sin embargo, la aplicación de una puerta Z nos proporciona el estado deseado $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="0a5c4-178">Si medimos y obtuvieron un resultado de __11, el tercer qubit, en__el estado $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="0a5c4-179">Esto difiere del __mensaje__previsto, pero la aplicación de una puerta not seguida de una puerta Z nos proporciona el estado deseado $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="0a5c4-180">En Resumen, si medimos y el primer qubit es 1, se aplica una puerta Z.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="0a5c4-181">Si medimos y el segundo qubit es 1, se aplica una puerta NOT.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="0a5c4-182">Resumen</span><span class="sxs-lookup"><span data-stu-id="0a5c4-182">Summary</span></span>
<span data-ttu-id="0a5c4-183">A continuación se muestra un circuito de Quantum de libro de texto que implementa la teleportabilidad.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="0a5c4-184">Si se mueve de izquierda a derecha, puede ver:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="0a5c4-185">Paso 1: desenredo __aquí__ y __allí__ aplicando una puerta HADAMARD y una puerta CNOT.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="0a5c4-186">Paso 2: enviar el __mensaje__ mediante una puerta CNOT y una puerta Hadamard.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="0a5c4-187">Paso 3: realizar una medición del primer y segundo qubits, __mensaje__ y __aquí__.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="0a5c4-188">Paso 4: aplicar una puerta NOT o una puerta Z, dependiendo del resultado de la medición en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

![' Teletranspórtate (MSG: qubit, ahí: qubit): unidad '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="0a5c4-190">Teleportabilidad de Quantum: código</span><span class="sxs-lookup"><span data-stu-id="0a5c4-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="0a5c4-191">Tenemos nuestro circuito para la teleportabilidad de Quantum:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-191">We have our circuit for quantum teleportation:</span></span>

![' Teletranspórtate (MSG: qubit, ahí: qubit): unidad '](~/media/teleportation.svg)

<span data-ttu-id="0a5c4-193">Ahora podemos traducir cada uno de los pasos de este circuito de Quantum en Q #.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="0a5c4-194">Paso 0: definición</span><span class="sxs-lookup"><span data-stu-id="0a5c4-194">Step 0: Definition</span></span>
<span data-ttu-id="0a5c4-195">Cuando se realiza la teleportabilidad, es necesario conocer el __mensaje__ que se desea enviar y dónde se desea enviarlo (__allí__).</span><span class="sxs-lookup"><span data-stu-id="0a5c4-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="0a5c4-196">Por esta razón, empezamos definiendo una nueva operación de teletransporta con dos qubits como argumentos, `msg` y `there`:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="0a5c4-197">También necesitamos asignar una `here` qubit que se logra con un bloque de `using`:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="0a5c4-198">Paso 1: creación de un estado desenredado</span><span class="sxs-lookup"><span data-stu-id="0a5c4-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="0a5c4-199">A continuación, podemos crear el par enenredado entre `here` y `there` mediante las operaciones @"microsoft.quantum.primitive.h" y @"microsoft.quantum.primitive.cnot":</span><span class="sxs-lookup"><span data-stu-id="0a5c4-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.primitive.h" and @"microsoft.quantum.primitive.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="0a5c4-200">Paso 2: enviar el mensaje</span><span class="sxs-lookup"><span data-stu-id="0a5c4-200">Step 2: Send the message</span></span>
<span data-ttu-id="0a5c4-201">Después usamos las siguientes $ \operatorname{CNOT} $ y $H $ Gates para pasar el mensaje qubit:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="0a5c4-202">Paso 3 & 4: medir e interpretar el resultado</span><span class="sxs-lookup"><span data-stu-id="0a5c4-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="0a5c4-203">Por último, usamos @"microsoft.quantum.primitive.m" para realizar las medidas y realizar las operaciones de puerta necesarias para obtener el estado deseado, como se indica en las instrucciones de `if`:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-203">Finally, we use @"microsoft.quantum.primitive.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

<span data-ttu-id="0a5c4-204">Esto finaliza la definición de nuestro operador de teleportabilidad, de modo que podemos desasignar `here`, finalizar el cuerpo y finalizar la operación.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-204">This finishes the definition of our teleportation operator, so we can deallocate `here`, end the body, and end the operation.</span></span>

```qsharp
    }
}
```
