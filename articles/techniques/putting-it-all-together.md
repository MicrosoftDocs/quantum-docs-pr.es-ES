---
title: Técnicas de Q - Ponerlo todo junto
description: Repase a través de un programa básico de Q que demuestra la teletransportación cuántica.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030572"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="1b55b-103">Putting It All Together: Teletransportation</span><span class="sxs-lookup"><span data-stu-id="1b55b-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="1b55b-104">Volvamos al ejemplo del circuito de teletransportación definido en [Circuitos Cuánticos.](xref:microsoft.quantum.concepts.circuits)</span><span class="sxs-lookup"><span data-stu-id="1b55b-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="1b55b-105">Vamos a usar esto para ilustrar los conceptos que hemos aprendido hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="1b55b-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="1b55b-106">A continuación se proporciona una explicación de la teletransportación cuántica para aquellos que no están familiarizados con la teoría, seguido de un tutorial de la implementación de código en Q.</span><span class="sxs-lookup"><span data-stu-id="1b55b-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="1b55b-107">Teletransportación cuántica: Teoría</span><span class="sxs-lookup"><span data-stu-id="1b55b-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="1b55b-108">La teletransportación cuántica es una técnica para enviar un estado cuántico desconocido (que nos referiremos como el __'mensaje')__ de un qubit en una ubicación a un qubit en otra ubicación (nos referiremos a estos qubits como __'aquí'__ y '__allí__', respectivamente).</span><span class="sxs-lookup"><span data-stu-id="1b55b-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="1b55b-109">Podemos representar nuestro __mensaje__ como un vector usando la notación Dirac:</span><span class="sxs-lookup"><span data-stu-id="1b55b-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="1b55b-110">$$ á ket,psi, á alpha, ket{0} +{1} ábeta, $$</span><span class="sxs-lookup"><span data-stu-id="1b55b-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="1b55b-111">El estado del __mensaje__ qubit es desconocido para nosotros, ya que no sabemos los valores de $-alpha$ y $-beta$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="1b55b-112">Paso 1: Crear un estado enredado</span><span class="sxs-lookup"><span data-stu-id="1b55b-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="1b55b-113">Para enviar el __mensaje__ necesitamos que el qubit __aquí__ se enrede con el qubit __allí__.</span><span class="sxs-lookup"><span data-stu-id="1b55b-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="1b55b-114">Esto se logra mediante la aplicación de una puerta Hadamard, seguido de una puerta CNOT.</span><span class="sxs-lookup"><span data-stu-id="1b55b-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="1b55b-115">Echemos un vistazo a las matemáticas detrás de estas operaciones de la puerta.</span><span class="sxs-lookup"><span data-stu-id="1b55b-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="1b55b-116">Comenzaremos con los qubits __aquí__ y __allá__ {0}tanto en el estado $-ket $.</span><span class="sxs-lookup"><span data-stu-id="1b55b-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="1b55b-117">Después de enredar estos qubits, se encuentran en el estado:</span><span class="sxs-lookup"><span data-stu-id="1b55b-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="1b55b-118">$$ á ket,phi,+ á{1}á frac sqrt{2}('ket{00} {11}+ 'ket' ) '$</span><span class="sxs-lookup"><span data-stu-id="1b55b-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="1b55b-119">Paso 2: Enviar el mensaje</span><span class="sxs-lookup"><span data-stu-id="1b55b-119">Step 2: Send the message</span></span>
<span data-ttu-id="1b55b-120">Para enviar el __mensaje__ primero aplicamos una puerta CNOT con el __mensaje__ qubit y __aquí__ qubit como entradas (el __mensaje__ qubit es el control y el __qubit aquí__ es el qubit objetivo, en este caso).</span><span class="sxs-lookup"><span data-stu-id="1b55b-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="1b55b-121">Este estado de entrada se puede escribir:</span><span class="sxs-lookup"><span data-stu-id="1b55b-121">This input state can be written:</span></span>

<span data-ttu-id="1b55b-122">$$ á ket, psi, ket, phi, etc., á{0} ('alpha''{1}''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''{1}{2}{00} {11}</span><span class="sxs-lookup"><span data-stu-id="1b55b-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="1b55b-123">Esto se expande a:</span><span class="sxs-lookup"><span data-stu-id="1b55b-123">This expands to:</span></span>

<span data-ttu-id="1b55b-124">$$ .ket, psi, ket, phi, phi, etc., etc. ,frac, alpha, sqrt,{2}ket , etc.{000} {2}{011} {2}{100} {2}{111}</span><span class="sxs-lookup"><span data-stu-id="1b55b-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="1b55b-125">Como recordatorio, la puerta CNOT voltea el qubit objetivo cuando el qubit de control es 1.</span><span class="sxs-lookup"><span data-stu-id="1b55b-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="1b55b-126">Por ejemplo, una entrada de{000}$-ket $ no dará lugar a ningún cambio ya que el primer qubit (el control) es 0.</span><span class="sxs-lookup"><span data-stu-id="1b55b-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="1b55b-127">Sin embargo, tome un caso en el que el{100}primer qubit es 1 - por ejemplo, una entrada de $-ket $.</span><span class="sxs-lookup"><span data-stu-id="1b55b-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="1b55b-128">En este caso, la salida{110}es $-ket $ como el segundo qubit (el objetivo) es volteado por la puerta CNOT.</span><span class="sxs-lookup"><span data-stu-id="1b55b-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="1b55b-129">Ahora vamos a considerar nuestra salida una vez que la puerta CNOT ha actuado en nuestra entrada anterior.</span><span class="sxs-lookup"><span data-stu-id="1b55b-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="1b55b-130">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b55b-130">The result is:</span></span>

<span data-ttu-id="1b55b-131">$$ á frac,{2}alpha, sqrt,{000} etc., etc. y áfrac,{2}alpha,{011} etc. y áclomenos, etc.{2}{110} {2}{101}</span><span class="sxs-lookup"><span data-stu-id="1b55b-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="1b55b-132">El siguiente paso para enviar el __mensaje__ es aplicar una puerta de Hadamard al __mensaje__ qubit (ese es el primer qubit de cada término).</span><span class="sxs-lookup"><span data-stu-id="1b55b-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="1b55b-133">Como recordatorio, la puerta de Hadamard hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b55b-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="1b55b-134">Entrada</span><span class="sxs-lookup"><span data-stu-id="1b55b-134">Input</span></span> | <span data-ttu-id="1b55b-135">Output</span><span class="sxs-lookup"><span data-stu-id="1b55b-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="1b55b-136">$-ket{0}$</span><span class="sxs-lookup"><span data-stu-id="1b55b-136">$\ket{0}$</span></span>  | <span data-ttu-id="1b55b-137">$-frac{1}ásqrt{2}('ket+{0} ''ket')'{1}</span><span class="sxs-lookup"><span data-stu-id="1b55b-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="1b55b-138">$-ket{1}$</span><span class="sxs-lookup"><span data-stu-id="1b55b-138">$\ket{1}$</span></span>  | <span data-ttu-id="1b55b-139">$-frac{1}ásqrt{2}(ket{0} - áket{1})$</span><span class="sxs-lookup"><span data-stu-id="1b55b-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="1b55b-140">Si aplicamos la puerta de Hadamard al primer qubit de cada término de nuestra salida anterior, obtenemos el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="1b55b-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="1b55b-141">$$ á frac, alpha, sqrt,{2}{1}etc., frac,{2}sqrt, etc. (ket{0} + ket{1})) , ket{00} {2}+ á{1}frac, alpha,{2}(frac,{0} alpha,{1}"frac"{11} y "sqrt" ("frac"{2}("ket" + "ket") (ket ) y "ket" (") frac-beta-sqrt{1}{2}(frac, sqrt, etc.,{1}{01} {0} "ket" y{1}"ket)", "ket", "ket", "ket",{10} "frac" y{2}"beta", "frac",{1}"frac", "sqrt"{2}("ket"{0} y "ket" )", "ket" $$</span><span class="sxs-lookup"><span data-stu-id="1b55b-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="1b55b-142">Tenga en cuenta que cada{1}término tiene{2}dos factores $-frac-sqrt-$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="1b55b-143">Podemos multiplicarlos dando el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="1b55b-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="1b55b-144">$$ á frac-alpha-('''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''{2}{0} {1}{00} {2}{0} {1}{11} {2}{0} {1}{10} {2}{0} {1}{01}</span><span class="sxs-lookup"><span data-stu-id="1b55b-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="1b55b-145">El factor{1}{2}$-frac $ es común a cada término, por lo que ahora podemos llevarlo fuera de los corchetes:</span><span class="sxs-lookup"><span data-stu-id="1b55b-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="1b55b-146">$${1}{2}áfrac ábig[-alpha('ket{0} {1}+ 'ket ''ket'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''{00} {0} {1}{11} {0} {1}{10} {0} {1}{01}</span><span class="sxs-lookup"><span data-stu-id="1b55b-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="1b55b-147">A continuación, podemos multiplicar los corchetes para cada término dando:</span><span class="sxs-lookup"><span data-stu-id="1b55b-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="1b55b-148">{1}{2}$$ áfrac ábig ['alpha'ket{000} +{100} ''alpha'ket +{011} ''alpha''ket + ''alpha'ket{111} + ''beta'ket'{010} ' ''beta'ket{110} + 'beta'ket'{001} '{101}</span><span class="sxs-lookup"><span data-stu-id="1b55b-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="1b55b-149">Paso 3: Mida el resultado</span><span class="sxs-lookup"><span data-stu-id="1b55b-149">Step 3: Measure the result</span></span>

<span data-ttu-id="1b55b-150">Debido a __que aquí__ y __allá__ se enredan, cualquier medida en __aquí__ afectará el estado de __allí.__</span><span class="sxs-lookup"><span data-stu-id="1b55b-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="1b55b-151">Si medimos el primer y segundo qubit (__mensaje__ y __aquí__) podemos aprender en qué estado __hay,__ debido a esta propiedad de enredo.</span><span class="sxs-lookup"><span data-stu-id="1b55b-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="1b55b-152">Si medimos y obtenemos un resultado 00, la superposición se contrae, dejando solo los términos coherentes con este resultado.</span><span class="sxs-lookup"><span data-stu-id="1b55b-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="1b55b-153">Eso es $-alpha-ket{000} +-beta-ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="1b55b-154">Esto se puede refactorizar{00}a $-ket{0} ('alpha'ket+'beta'ket{1}''$' .</span><span class="sxs-lookup"><span data-stu-id="1b55b-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="1b55b-155">Por lo tanto, si medimos el primer y segundo qubit para que sea 00, sabemos{0} que el tercer{1}qubit, __allí__, está en el estado $('alpha'ket +'beta'ket )$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="1b55b-156">Si medimos y obtenemos un resultado 01, la superposición se contrae, dejando solo los términos coherentes con este resultado.</span><span class="sxs-lookup"><span data-stu-id="1b55b-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="1b55b-157">Eso es $-alpha-ket{011} +-beta-ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="1b55b-158">Esto se puede refactorizar{01}a $-ket{1} ('alpha'ket+'beta'ket{0}''$' .</span><span class="sxs-lookup"><span data-stu-id="1b55b-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="1b55b-159">Por lo tanto, si medimos el primer y segundo qubit para que sea 01, sabemos{1} que el tercer{0}qubit, __allí__, está en el estado $('alpha'ket +'beta'ket )$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="1b55b-160">Si medimos y obtenemos un resultado 10, la superposición colapsa, dejando solo términos consistentes con este resultado.</span><span class="sxs-lookup"><span data-stu-id="1b55b-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="1b55b-161">Eso es $-alpha-ket{100} --beta-ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="1b55b-162">Esto se puede refactorizar{10}a $-ket{0} ('alpha'ket{1}''beta'ket ''$' .</span><span class="sxs-lookup"><span data-stu-id="1b55b-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="1b55b-163">Por lo tanto, si medimos el primer y segundo qubit para que sea 10, sabemos{0} que el tercer{1}qubit, __allí__, está en el estado $('alpha'ket -'beta'ket )$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="1b55b-164">Si medimos y obtenemos un resultado 11, la superposición colapsa, dejando solo términos consistentes con este resultado.</span><span class="sxs-lookup"><span data-stu-id="1b55b-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="1b55b-165">Eso es $-alpha-ket{111} --beta-ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="1b55b-166">Esto se puede refactorizar{11}a $-ket{1} ('alpha'ket{0}''beta'ket ''$' .</span><span class="sxs-lookup"><span data-stu-id="1b55b-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="1b55b-167">Por lo tanto, si medimos el primer y segundo qubit para que sea 11, sabemos{1} que el tercer{0}qubit, __allí__, está en el estado $('alpha'ket -'beta'ket )$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="1b55b-168">Paso 4: Interpretar el resultado</span><span class="sxs-lookup"><span data-stu-id="1b55b-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="1b55b-169">Como recordatorio, el __mensaje__ original que deseamos enviar era:</span><span class="sxs-lookup"><span data-stu-id="1b55b-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="1b55b-170">$$ á ket,psi, á alpha, ket{0} +{1} ábeta, $$</span><span class="sxs-lookup"><span data-stu-id="1b55b-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="1b55b-171">Tenemos que poner el __qubit allí__ en este estado, para que el estado recibido sea el que se pretendía.</span><span class="sxs-lookup"><span data-stu-id="1b55b-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="1b55b-172">Si medimos y obtuvimos un resultado de 00, entonces el tercer qubit, __allí__, está en el estado $('alpha'ket{0} +'beta'ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="1b55b-173">Como este es el __mensaje__previsto, no se requiere ninguna alteración.</span><span class="sxs-lookup"><span data-stu-id="1b55b-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="1b55b-174">Si medimos y obtuvimos un resultado de 01, entonces el tercer qubit, __allí__, está en el estado $('alpha'ket{1} +'beta'ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="1b55b-175">Esto difiere del __mensaje__previsto, sin embargo, la aplicación de una{0} puerta NOT nos{1}da el estado deseado $('alpha'ket+'beta'ket )$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="1b55b-176">Si medimos y obtuvimos un resultado de 10, entonces el tercer qubit, __allí__, está en el estado $('alpha'ket{0} -'beta'ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="1b55b-177">Esto difiere del __mensaje__previsto, sin embargo, la aplicación de una{0} puerta Z nos{1}da el estado deseado $('alpha'ket +'beta'ket )$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="1b55b-178">Si medimos y obtuvimos un resultado de 11, entonces el tercer qubit, __allí__, está en el estado $('alpha'ket{1} -'beta'ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="1b55b-179">Esto difiere del __mensaje__previsto, sin embargo, la aplicación de una puerta NOT seguida{0} de una puerta{1}Z nos da el estado deseado $(-alpha-ket +-beta-ket )$.</span><span class="sxs-lookup"><span data-stu-id="1b55b-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="1b55b-180">En resumen, si medimos y el primer qubit es 1, se aplica una puerta Z.</span><span class="sxs-lookup"><span data-stu-id="1b55b-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="1b55b-181">Si medimos y el segundo qubit es 1, se aplica una puerta NOT.</span><span class="sxs-lookup"><span data-stu-id="1b55b-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="1b55b-182">Resumen</span><span class="sxs-lookup"><span data-stu-id="1b55b-182">Summary</span></span>
<span data-ttu-id="1b55b-183">A continuación se muestra un circuito cuántico de libro de texto que implementa la teletransportación.</span><span class="sxs-lookup"><span data-stu-id="1b55b-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="1b55b-184">Pasando de izquierda a derecha se puede ver:</span><span class="sxs-lookup"><span data-stu-id="1b55b-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="1b55b-185">Paso 1: Enredado __aquí__ y __allá__ mediante la aplicación de una puerta Hadamard y puerta CNOT.</span><span class="sxs-lookup"><span data-stu-id="1b55b-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="1b55b-186">Paso 2: Enviar el __mensaje__ usando una puerta CNOT y una puerta Hadamard.</span><span class="sxs-lookup"><span data-stu-id="1b55b-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="1b55b-187">Paso 3: Tomando una medida del primer y segundo qubits, __mensaje__ y __aquí__.</span><span class="sxs-lookup"><span data-stu-id="1b55b-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="1b55b-188">Paso 4: Aplicar una puerta NO o una puerta Z, dependiendo del resultado de la medición en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="1b55b-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!['Teleport(msg : Qubit, hay : Qubit) : Unidad'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="1b55b-190">Teletransportación cuántica: Código</span><span class="sxs-lookup"><span data-stu-id="1b55b-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="1b55b-191">Tenemos nuestro circuito de teletransportación cuántica:</span><span class="sxs-lookup"><span data-stu-id="1b55b-191">We have our circuit for quantum teleportation:</span></span>

!['Teleport(msg : Qubit, hay : Qubit) : Unidad'](~/media/teleportation.svg)

<span data-ttu-id="1b55b-193">Ahora podemos traducir cada uno de los pasos de este circuito cuántico en Q.</span><span class="sxs-lookup"><span data-stu-id="1b55b-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="1b55b-194">Paso 0: Definición</span><span class="sxs-lookup"><span data-stu-id="1b55b-194">Step 0: Definition</span></span>
<span data-ttu-id="1b55b-195">Cuando realizamos la teletransportación, debemos conocer el __mensaje__ que deseamos enviar, y dónde queremos enviarlo __(allí).__</span><span class="sxs-lookup"><span data-stu-id="1b55b-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="1b55b-196">Por esta razón, comenzamos definiendo una nueva operación de Teletransporte `msg` `there`a la que se le dan dos qubits como argumentos, y:</span><span class="sxs-lookup"><span data-stu-id="1b55b-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="1b55b-197">También necesitamos asignar un `here` qubit que `using` logramos con un bloque:</span><span class="sxs-lookup"><span data-stu-id="1b55b-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="1b55b-198">Paso 1: Crear un estado enredado</span><span class="sxs-lookup"><span data-stu-id="1b55b-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="1b55b-199">A continuación, podemos crear el `here` `there` par entre @"microsoft.quantum.intrinsic.h" @"microsoft.quantum.intrinsic.cnot" y mediante las operaciones:</span><span class="sxs-lookup"><span data-stu-id="1b55b-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="1b55b-200">Paso 2: Enviar el mensaje</span><span class="sxs-lookup"><span data-stu-id="1b55b-200">Step 2: Send the message</span></span>
<span data-ttu-id="1b55b-201">A continuación, usamos las siguientes puertas $-nombredeusuario-CNOT-$ y $H$ para mover nuestro mensaje qubit:</span><span class="sxs-lookup"><span data-stu-id="1b55b-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="1b55b-202">Paso 3 & 4: Medición e interpretación del resultado</span><span class="sxs-lookup"><span data-stu-id="1b55b-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="1b55b-203">Por último, @"microsoft.quantum.intrinsic.m" utilizamos para realizar las mediciones y realizar las operaciones `if` de puerta necesarias para obtener el estado deseado, como se indica mediante instrucciones:</span><span class="sxs-lookup"><span data-stu-id="1b55b-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a><span data-ttu-id="1b55b-204">Paso 5: Reiniciar el registro qubit</span><span class="sxs-lookup"><span data-stu-id="1b55b-204">Step 5: Restarting the qubit register</span></span>

<span data-ttu-id="1b55b-205">Al final de cada operación de Q, tenemos que{0}dejar que los qubits en el estado $-ket $.</span><span class="sxs-lookup"><span data-stu-id="1b55b-205">At the end of every Q# operation we need to let the qubits in the state $\ket{0}$.</span></span> <span data-ttu-id="1b55b-206">Podemos usar @"microsoft.quantum.intrinsic.reset" para reiniciar todos los qubits al estado cero y esto terminará nuestra operación.</span><span class="sxs-lookup"><span data-stu-id="1b55b-206">We can use @"microsoft.quantum.intrinsic.reset" to restart all the qubits to the zero state and this will finish our operation.</span></span>

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


