---
title: Descripción de la computación cuántica
description: ¿Qué son los equipos cuánticos y cómo usan los principios de la mecánica cuántica?
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.understanding
ms.openlocfilehash: 65fa85a80021124444fd352f9492d03cbefcb859
ms.sourcegitcommit: a03d79ca3f0774161a9f86a15528d36e1291acce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83433017"
---
# <a name="understanding-quantum-computing"></a><span data-ttu-id="6240e-103">Descripción de la computación cuántica</span><span class="sxs-lookup"><span data-stu-id="6240e-103">Understanding quantum computing</span></span>

<span data-ttu-id="6240e-104">La computación cuántica usa los principios de la mecánica cuántica para procesar la información.</span><span class="sxs-lookup"><span data-stu-id="6240e-104">Quantum computing uses the principles of quantum mechanics to process information.</span></span> <span data-ttu-id="6240e-105">Por este motivo, la computación cuántica requiere un enfoque diferente de la computación clásica.</span><span class="sxs-lookup"><span data-stu-id="6240e-105">Because of this, quantum computing requires a different approach than classical computing.</span></span>  <span data-ttu-id="6240e-106">Un ejemplo de esta diferencia es el procesador que usan los equipos cuánticos.</span><span class="sxs-lookup"><span data-stu-id="6240e-106">One example of this difference is the processor used in quantum computers.</span></span>  <span data-ttu-id="6240e-107">Los equipos clásicos usan los conocidos chips de silicio, mientras que los equipos cuánticos usan materiales cuánticos como átomos, iones o electrones.</span><span class="sxs-lookup"><span data-stu-id="6240e-107">Where classical computers use familiar silicon-based chips, quantum computers use quantum materials such as atoms, ions, photons, or electrons.</span></span>  

<span data-ttu-id="6240e-108">El material cuántico se comporta de acuerdo con las leyes de las mecánicas cuántica, lo que permite aprovechar conceptos como la computación probabilística, la superposición y el entrelazamiento.</span><span class="sxs-lookup"><span data-stu-id="6240e-108">The quantum material behaves according to the laws of quantum mechanics, leveraging concepts such as probabilistic computation, superposition, and entanglement.</span></span> <span data-ttu-id="6240e-109">Estos conceptos son la base de los algoritmos cuánticos, que aprovechan la eficacia de la computación cuántica para solucionar problemas complejos.</span><span class="sxs-lookup"><span data-stu-id="6240e-109">These concepts provide the basis for quantum algorithms that harness the power of quantum computing to solve complex problems.</span></span> <span data-ttu-id="6240e-110">En este artículo se describen algunos de los conceptos esenciales de la mecánica cuántica en la que se basa la computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="6240e-110">This article describes some of the essential concepts of quantum mechanics on which quantum computing is based.</span></span>

## <a name="a-birds-eye-view-of-quantum-mechanics"></a><span data-ttu-id="6240e-111">Un vistazo rápido a la mecánica cuántica</span><span class="sxs-lookup"><span data-stu-id="6240e-111">A bird’s-eye view of quantum mechanics</span></span>

<span data-ttu-id="6240e-112">La mecánica cuántica, también llamada teoría cuántica, es una rama de la física que se ocupa de las partículas en los niveles atómico y subatómico.</span><span class="sxs-lookup"><span data-stu-id="6240e-112">Quantum mechanics, also called quantum theory, is a branch of physics that deals with particles at the atomic and subatomic levels.</span></span> <span data-ttu-id="6240e-113">Sin embargo, en el nivel cuántico, no se aplican muchas de las leyes de la mecánica que se dan por hechas.</span><span class="sxs-lookup"><span data-stu-id="6240e-113">At the quantum level, however, many of the laws of mechanics you take for granted don’t apply.</span></span> <span data-ttu-id="6240e-114">La superposición, la medición cuántica y el entrelazamiento son tres fenómenos fundamentales de la computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="6240e-114">Superposition, quantum measurement, and entanglement are three phenomena that are central to quantum computing.</span></span>  

### <a name="superposition-vs-binary-computing"></a><span data-ttu-id="6240e-115">Superposición frente a computación binaria</span><span class="sxs-lookup"><span data-stu-id="6240e-115">Superposition vs. binary computing</span></span>

<span data-ttu-id="6240e-116">Imagine que está haciendo ejercicio en su salón.</span><span class="sxs-lookup"><span data-stu-id="6240e-116">Imagine that you are exercising in your living room.</span></span> <span data-ttu-id="6240e-117">Gira completamente a la izquierda y, a continuación, gira completamente a la derecha.</span><span class="sxs-lookup"><span data-stu-id="6240e-117">You turn all the way to your left and then all the way to your right.</span></span> <span data-ttu-id="6240e-118">Ahora, gire a la izquierda y a la derecha al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="6240e-118">Now turn to your left and your right at the same time.</span></span> <span data-ttu-id="6240e-119">No se puede (no sin dividirse en dos, al menos).</span><span class="sxs-lookup"><span data-stu-id="6240e-119">You can’t do it (not without splitting yourself in two, at least).</span></span>  <span data-ttu-id="6240e-120">Obviamente, no puede estar en ambos estados a la vez: no puede estar mirando a la izquierda y a la derecha al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="6240e-120">Obviously, you can’t be in both of those states at once – you can’t be facing left and facing right at the same time.</span></span>

<span data-ttu-id="6240e-121">Sin embargo, si fuera una partícula cuántica, tendría una probabilidad determinada de estar *mirando a la izquierda* y una probabilidad determinada de estar *mirando a la derecha* debido a un fenómeno conocido como **superposición** (o también **coherencia**).</span><span class="sxs-lookup"><span data-stu-id="6240e-121">However, if you are a quantum particle, then you can have a certain probability of *facing left* AND a certain probability of *facing right* due to a phenomenon known as **superposition** (also known as **coherence**).</span></span>

<span data-ttu-id="6240e-122">Una partícula cuántica, como el electrón, tiene sus propias propiedades "orientadas a la izquierda o a la derecha", por ejemplo el **espín**, que se conoce como arriba o abajo o, en el ámbito de la informática binaria clásica, simplemente 1 o 0.</span><span class="sxs-lookup"><span data-stu-id="6240e-122">A quantum particle such as an electron has its own “facing left or facing right” properties, for example **spin**, referred to as either up or down, or to make it more relatable to classical binary computing, let’s just say 1 or 0.</span></span> <span data-ttu-id="6240e-123">Cuando una partícula cuántica está en un estado de superposición, se trata de una combinación lineal de un número infinito de estados entre 1 y 0, pero no se sabe cuál será hasta que realmente se mire, lo que nos lleva al siguiente fenómeno, la **medición cuántica**.</span><span class="sxs-lookup"><span data-stu-id="6240e-123">When a quantum particle is in a superposition state, it’s a linear combination of an infinite number of states between 1 and 0, but you don’t know which one it will be until you actually look at it, which brings up our next phenomenon, **quantum measurement**.</span></span>

### <a name="quantum-measurement"></a><span data-ttu-id="6240e-124">Medición cuántica</span><span class="sxs-lookup"><span data-stu-id="6240e-124">Quantum measurement</span></span>

<span data-ttu-id="6240e-125">Ahora, supongamos que un amigo quiere hacerle una foto mientras hace ejercicio.</span><span class="sxs-lookup"><span data-stu-id="6240e-125">Now, let’s say your friend comes over and wants to take a picture of you exercising.</span></span> <span data-ttu-id="6240e-126">Lo más probable es que obtenga una imagen borrosa de usted girando, en algún lugar entre la izquierda y la derecha.</span><span class="sxs-lookup"><span data-stu-id="6240e-126">Most likely, they’ll get a blurry image of you turning somewhere between all the way left and all the way right.</span></span>

<span data-ttu-id="6240e-127">Pero si fuera un objeto cuántico, se produce algo interesante.</span><span class="sxs-lookup"><span data-stu-id="6240e-127">But if you’re a quantum particle, an interesting thing happens.</span></span> <span data-ttu-id="6240e-128">Sea cual sea el lugar en el que se encuentre cuando le hagan la foto, siempre se mostrará totalmente girado a la izquierda o a la derecha, sin nada en medio.</span><span class="sxs-lookup"><span data-stu-id="6240e-128">No matter where you are when they take the picture, it will always show you either all the way left or all the way right – nothing in-between.</span></span>

<span data-ttu-id="6240e-129">Esto se debe a que la acción de observar o medir un objeto cuántico **colapsa** el estado de superposición (lo que también se conoce como **decoherencia**) y la partícula toma un estado binario clásico de 1 o 0.</span><span class="sxs-lookup"><span data-stu-id="6240e-129">This is because the act of observing or measuring a quantum particle **collapses** the superposition state (also known as **decoherence**) and the particle takes on a classical binary state of either 1 or 0.</span></span>

<span data-ttu-id="6240e-130">Este estado binario es útil, porque en computación se pueden hacer muchas cosas con 1 y 0.</span><span class="sxs-lookup"><span data-stu-id="6240e-130">This binary state is helpful to us, because in computing you can do lots of things with 1’s and 0’s.</span></span> <span data-ttu-id="6240e-131">Sin embargo, una vez que una partícula cuántica se ha medido y ha colapsado, permanece en ese estado siempre (al igual que la imagen) y siempre será 1 o 0.</span><span class="sxs-lookup"><span data-stu-id="6240e-131">However, once a quantum particle has been measured and collapsed, it stays in that state forever (just like your picture) and will always be a 1 or 0.</span></span> <span data-ttu-id="6240e-132">Sin embargo, como veremos más adelante, en computación cuántica hay operaciones que pueden "restablecer" una partícula de nuevo al estado de superposición para poder usarla de nuevo para los cálculos cuánticos.</span><span class="sxs-lookup"><span data-stu-id="6240e-132">As you’ll see later, though, in quantum computing there are operations that can “reset” a particle back to a superposition state so it can be used for quantum calculations again.</span></span>

### <a name="entanglement"></a><span data-ttu-id="6240e-133">Entrelazamiento</span><span class="sxs-lookup"><span data-stu-id="6240e-133">Entanglement</span></span>

<span data-ttu-id="6240e-134">El fenómeno más interesante de la mecánica cuántica probablemente sea la capacidad que dos o más partículas cuánticas tienen de **entrelazarse**.</span><span class="sxs-lookup"><span data-stu-id="6240e-134">Possibly the most interesting phenomenon of quantum mechanics is the ability of two or more quantum particles to become **entangled** with each other.</span></span> <span data-ttu-id="6240e-135">Cuando los objetos se entrelazan, forman un único sistema, de modo que el estado cuántico de cualquiera de las partículas no se puede describir independientemente del estado cuántico de las demás.</span><span class="sxs-lookup"><span data-stu-id="6240e-135">When particles become entangled, they form a single system such that the quantum state of any one particle cannot be described independently of the quantum state of the other particles.</span></span> <span data-ttu-id="6240e-136">Esto significa que cualquier operación o proceso que se aplique a una partícula se correlaciona también con las demás.</span><span class="sxs-lookup"><span data-stu-id="6240e-136">This means that whatever operation or process you apply to one particle correlates to the other particles as well.</span></span>

<span data-ttu-id="6240e-137">Además de esta interdependencia, las partículas pueden mantener esta conexión, aunque se separen a distancias increíblemente grandes, incluso a años luz.</span><span class="sxs-lookup"><span data-stu-id="6240e-137">In addition to this interdependency, particles can maintain this connection even when separated over incredibly large distances, even light-years.</span></span> <span data-ttu-id="6240e-138">Los efectos de la medición cuántica también se aplican a las partículas entrelazadas, de modo que cuando se mide una partícula y colapsa, la otra partícula también colapsa.</span><span class="sxs-lookup"><span data-stu-id="6240e-138">The effects of quantum measurement also apply to entangled particles, such that when one particle is measured and collapses, the other particle collapses as well.</span></span> <span data-ttu-id="6240e-139">Dado que hay una correlación entre los cúbits entrelazados, al medir el estado de un cúbit se obtiene información sobre el estado del otro cúbit; esta propiedad concreta es muy útil en la computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="6240e-139">Because there is a correlation between the entangled qubits, measuring the state of one qubit provides information about the state of the other qubit – this particular property is very helpful in quantum computing.</span></span>

### <a name="qubits-and-probability"></a><span data-ttu-id="6240e-140">Cúbits y probabilidad</span><span class="sxs-lookup"><span data-stu-id="6240e-140">Qubits and probability</span></span>

<span data-ttu-id="6240e-141">Los equipos clásicos almacenan y procesan información en bits, que pueden tener un estado de 1 o 0, pero nunca ambos.</span><span class="sxs-lookup"><span data-stu-id="6240e-141">Classical computers store and process information in bits, which can have a state of either 1 or 0, but never both.</span></span> <span data-ttu-id="6240e-142">El equivalente en la computación cuántica es el **cúbit**, que representa el estado de una partícula cuántica.</span><span class="sxs-lookup"><span data-stu-id="6240e-142">The equivalent in quantum computing is the **qubit**, which represents the state of a quantum particle.</span></span> <span data-ttu-id="6240e-143">Debido a la superposición, cúbits puede ser 1 o 0 o cualquier cosa entre ellos.</span><span class="sxs-lookup"><span data-stu-id="6240e-143">Because of superposition, qubits can either be 1 or 0 or anything in between.</span></span> <span data-ttu-id="6240e-144">En función de su configuración, un cúbit tiene una determinada *probabilidad* de colapsar en 1 o 0.</span><span class="sxs-lookup"><span data-stu-id="6240e-144">Depending on its configuration, a qubit has a certain *probability* of collapsing to 1 or 0.</span></span> <span data-ttu-id="6240e-145">La probabilidad de que un cúbit colapse en una u otra forma está determinada por la **interferencia cuántica**.</span><span class="sxs-lookup"><span data-stu-id="6240e-145">The qubit's probability of collapsing one way or the other is determined by **quantum interference**.</span></span> 

<span data-ttu-id="6240e-146">¿Recuerda el amigo que le estaba haciendo la foto?</span><span class="sxs-lookup"><span data-stu-id="6240e-146">Remember your friend that was taking your picture?</span></span> <span data-ttu-id="6240e-147">Supongamos que tiene unos filtros especiales en su cámara llamados filtros de *interferencia*.</span><span class="sxs-lookup"><span data-stu-id="6240e-147">Suppose they have special filters on their camera called *Interference* filters.</span></span> <span data-ttu-id="6240e-148">Si selecciona el filtro *70/30* y empieza a hacer fotos, en el 70 % de ellas se le verá a la izquierda y, en un 30 % se le verá a la derecha.</span><span class="sxs-lookup"><span data-stu-id="6240e-148">If they select the *70/30* filter and start taking pictures, in 70% of them you will be facing left, and in 30% you will be facing right.</span></span> <span data-ttu-id="6240e-149">El filtro ha interferido con el estado normal de la cámara y ha influido en la probabilidad de su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="6240e-149">The filter has interfered with the regular state of the camera to influence the probability of its behavior.</span></span>

<span data-ttu-id="6240e-150">Del mismo modo, la interferencia cuántica afecta al estado de un cúbit e influye en la probabilidad de un determinado resultado durante la medición. En este estado probabilístico es donde destacan las capacidades de la informática cuántica.</span><span class="sxs-lookup"><span data-stu-id="6240e-150">Similarly, quantum interference affects the state of a qubit in order to influence the probability of a certain outcome during measurement, and this probabilistic state is where the power of quantum computing excels.</span></span>

<span data-ttu-id="6240e-151">Por ejemplo, con dos bits en un equipo clásico, cada bit puede almacenar 1 o 0, por lo que juntos puede almacenar cuatro valores posibles: **00**, **01**, **10** y **11**, pero solo uno de ellos a la vez.</span><span class="sxs-lookup"><span data-stu-id="6240e-151">For example, with two bits in a classical computer, each bit can store 1 or 0, so together you can store four possible values – **00**, **01**, **10**, and **11** – but only one of those at a time.</span></span> <span data-ttu-id="6240e-152">Sin embargo, con dos cúbits en superposición, cada cúbit puede ser 1 o 0 o *ambos*, por lo que se pueden representar los mismos cuatro valores simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="6240e-152">With two qubits in superposition, however, each qubit can be 1 or 0 or *both*, so you can represent the same four values simultaneously.</span></span> <span data-ttu-id="6240e-153">Con tres cúbits, se pueden representar ocho valores, con cuatro cúbits, puede representar 16 valores, etc.</span><span class="sxs-lookup"><span data-stu-id="6240e-153">With three qubits, you can represent eight values, with four qubits, you can represent 16 values, and so on.</span></span>

## <a name="summary"></a><span data-ttu-id="6240e-154">Resumen</span><span class="sxs-lookup"><span data-stu-id="6240e-154">Summary</span></span>

<span data-ttu-id="6240e-155">Estos conceptos solo una pequeñísima muestra de la mecánica cuántica, pero son conceptos importantes que hay que conocer para trabajar con la computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="6240e-155">These concepts just scratch the surface of quantum mechanics, but are fundamentally important concepts to know for quantum computing.</span></span>

- <span data-ttu-id="6240e-156">**Superposición**: capacidad de las partículas cuánticas para ser una combinación de todos los estados posibles.</span><span class="sxs-lookup"><span data-stu-id="6240e-156">**Superposition** - The ability of quantum particles to be a combination of all possible states.</span></span>
- <span data-ttu-id="6240e-157">**Medición cuántica**: acto de observar una partícula cuántica en superposición y producir uno de los estados posibles.</span><span class="sxs-lookup"><span data-stu-id="6240e-157">**Quantum measurement** - The act of observing a quantum particle in superposition and resulting in one of the possible states.</span></span>
- <span data-ttu-id="6240e-158">**Entrelazamiento**: capacidad de las partículas cuánticas para correlacionar entre sí los resultados de la medición.</span><span class="sxs-lookup"><span data-stu-id="6240e-158">**Entanglement** - The ability of quantum particles to correlate their measurement results with each other.</span></span>
- <span data-ttu-id="6240e-159">**Cúbit**: unidad básica de información en la computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="6240e-159">**Qubit** - The basic unit of information in quantum computing.</span></span> <span data-ttu-id="6240e-160">Un cúbit representa una partícula cuántica en superposición de todos los estados posibles.</span><span class="sxs-lookup"><span data-stu-id="6240e-160">A qubit represents a quantum particle in superposition of all possible states.</span></span>
- <span data-ttu-id="6240e-161">**Interferencia**: comportamiento intrínseco de un cúbit debido a la influencia de la superposición en la probabilidad de que colapse en una forma u otra.</span><span class="sxs-lookup"><span data-stu-id="6240e-161">**Interference** - Intrinsic behavior of a qubit due to superposition to influence the probability of it collapsing one way or another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6240e-162">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6240e-162">Next Steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6240e-163">Simuladores y equipos cuánticos</span><span class="sxs-lookup"><span data-stu-id="6240e-163">Quantum computers and quantum simulators</span></span>](xref:microsoft.quantum.overview.simulators)