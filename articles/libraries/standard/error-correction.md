---
title: 'Bibliotecas de Q # Standard: corrección de errores | Microsoft Docs'
description: 'Bibliotecas de preguntas y respuestas estándar: corrección de errores'
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5aac40686ba9b45a51e0274a1828f2ff7cce6fc3
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184447"
---
# <a name="error-correction"></a><span data-ttu-id="ca11a-103">Corrección de errores</span><span class="sxs-lookup"><span data-stu-id="ca11a-103">Error Correction</span></span> #

## <a name="introduction"></a><span data-ttu-id="ca11a-104">Presentación</span><span class="sxs-lookup"><span data-stu-id="ca11a-104">Introduction</span></span> ##

<span data-ttu-id="ca11a-105">En informática clásica, si desea proteger un poco de los errores, a menudo es suficiente para representar ese bit por un *bit lógico* repitiendo el bit de datos.</span><span class="sxs-lookup"><span data-stu-id="ca11a-105">In classical computing, if one wants to protect a bit against errors, it can often suffice to represent that bit by a *logical bit* by repeating the data bit.</span></span>
<span data-ttu-id="ca11a-106">Por ejemplo, supongamos que $ \overline{0} = $0 es la codificación del bit de datos 0, donde usamos una línea por encima de la etiqueta 0 para indicar que es una codificación de un bit en el estado 0.</span><span class="sxs-lookup"><span data-stu-id="ca11a-106">For instance, let $\overline{0} = 000$ be the encoding of the data bit 0, where we use the a line above the label 0 to indicate that it is an encoding of a bit in the 0 state.</span></span>
<span data-ttu-id="ca11a-107">Si, de igual forma, se permite que $ \overline{1} = $111, tenemos un código de repetición simple que protege frente a un error de volteo de un bit.</span><span class="sxs-lookup"><span data-stu-id="ca11a-107">If we similarly let $\overline{1} = 111$, then we have a simple repetition code that protects against any one bit flip error.</span></span>
<span data-ttu-id="ca11a-108">Es decir, si se voltea cualquiera de los tres bits, se puede recuperar el estado del bit lógico tomando un voto mayoritario.</span><span class="sxs-lookup"><span data-stu-id="ca11a-108">That is, if any of the three bits are flipped, then we can recover the state of the logical bit by taking a majority vote.</span></span>
<span data-ttu-id="ca11a-109">Aunque la corrección de errores clásicas es un asunto mucho más rico que este ejemplo concreto (se recomienda la [Introducción a la descodificación de la descodificación](https://www.springer.com/us/book/9783540641339)), el código de repetición anterior ya señala a un posible problema al proteger la información de Quantum.</span><span class="sxs-lookup"><span data-stu-id="ca11a-109">Though classical error correction is a much richer subject that this particular example (we recommend [Lint's introduction to coding theory](https://www.springer.com/us/book/9783540641339)), the repetition code above already points to a possible problem in protecting quantum information.</span></span>
<span data-ttu-id="ca11a-110">Es decir, el [teorema sin clonación](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) implica que, si se mide cada qubit individual y se toma una votación mayoritaria por analogía con el código clásico anterior, se ha perdido la información precisa que se está intentando proteger.</span><span class="sxs-lookup"><span data-stu-id="ca11a-110">Namely, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) implies that if we measure each individual qubit and take a majority vote by analogy to classical code above, then we have lost the precise information that we are trying to protect.</span></span>

<span data-ttu-id="ca11a-111">En el valor de Quantum, veremos que la medida es problemática.</span><span class="sxs-lookup"><span data-stu-id="ca11a-111">In the quantum setting, we will see that the measurement is problematic.</span></span> <span data-ttu-id="ca11a-112">Todavía podemos implementar la codificación anterior.</span><span class="sxs-lookup"><span data-stu-id="ca11a-112">We can still implement the encoding above.</span></span>
<span data-ttu-id="ca11a-113">Es útil hacerlo para ver cómo se puede generalizar la corrección de errores en el caso de Quantum.</span><span class="sxs-lookup"><span data-stu-id="ca11a-113">It is helpful to do so to see how we can generalize error correction to the quantum case.</span></span>
<span data-ttu-id="ca11a-114">Por lo tanto, Let $ \ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$ y Let $ \ket{\overline{1}} = \ket{111}$.</span><span class="sxs-lookup"><span data-stu-id="ca11a-114">Thus, let $\ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$, and let $\ket{\overline{1}} = \ket{111}$.</span></span>
<span data-ttu-id="ca11a-115">Después, por linealidad, hemos definido el código de repetición para todas las entradas. por ejemplo, $ \ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}})/\sqrt{2} = (\ket{000} + \ket{111})/\sqrt{2}$.</span><span class="sxs-lookup"><span data-stu-id="ca11a-115">Then, by linearity, we have defined our repetition code for all inputs; for instance, $\ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}}) / \sqrt{2} = (\ket{000} + \ket{111}) / \sqrt{2}$.</span></span>
<span data-ttu-id="ca11a-116">En concreto, si se permite un error de volteo de bits $X _ 1 $ Act en el centro qubit, vemos que la corrección necesaria en ambas ramas es precisamente $X _ 1 _ 1: $ $ \begin{align} x_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left (x_1 \ket{000} + x_1 \ket @no__ t_3_ \right) \\\\ & = \frac{1}{\sqrt{2}} \left (\ket{010} + \ket{101} \right).</span><span class="sxs-lookup"><span data-stu-id="ca11a-116">In particular, letting a bit-flip error $X_1$ act on the middle qubit, we see that the correction needed in both branches is precisely $X_1$: $$ \begin{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left( X_1 \ket{000} + X_1 \ket{111} \right) \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{010} + \ket{101} \right).</span></span>
<span data-ttu-id="ca11a-117">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="ca11a-117">\end{align} $$</span></span>

<span data-ttu-id="ca11a-118">Para ver cómo podemos identificar que este es el caso sin medir el estado que estamos intentando proteger, es útil anotar qué hace cada error de volteo de bits diferente en los Estados lógicos:</span><span class="sxs-lookup"><span data-stu-id="ca11a-118">To see how we can identify that this is the case without measuring the very state we are trying to protect, it is helpful to write down what each different bit flip error does to our logical states:</span></span>

| <span data-ttu-id="ca11a-119">Error $E $</span><span class="sxs-lookup"><span data-stu-id="ca11a-119">Error $E$</span></span> | <span data-ttu-id="ca11a-120">$E \ket{\overline{0}} $</span><span class="sxs-lookup"><span data-stu-id="ca11a-120">$E\ket{\overline{0}}$</span></span> | <span data-ttu-id="ca11a-121">$E \ket{\overline{1}} $</span><span class="sxs-lookup"><span data-stu-id="ca11a-121">$E\ket{\overline{1}}$</span></span> |
| --- | --- | --- |
| <span data-ttu-id="ca11a-122">$ \boldone $</span><span class="sxs-lookup"><span data-stu-id="ca11a-122">$\boldone$</span></span> | <span data-ttu-id="ca11a-123">$ \ket{000}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-123">$\ket{000}$</span></span> | <span data-ttu-id="ca11a-124">$ \ket{111}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-124">$\ket{111}$</span></span> |
| <span data-ttu-id="ca11a-125">$X _0 $</span><span class="sxs-lookup"><span data-stu-id="ca11a-125">$X_0$</span></span> | <span data-ttu-id="ca11a-126">$ \ket{100}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-126">$\ket{100}$</span></span> | <span data-ttu-id="ca11a-127">$ \ket{011}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-127">$\ket{011}$</span></span> |
| <span data-ttu-id="ca11a-128">$X _ 1 _ $</span><span class="sxs-lookup"><span data-stu-id="ca11a-128">$X_1$</span></span> | <span data-ttu-id="ca11a-129">$ \ket{010}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-129">$\ket{010}$</span></span> | <span data-ttu-id="ca11a-130">$ \ket{101}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-130">$\ket{101}$</span></span> |
| <span data-ttu-id="ca11a-131">$X _2 $</span><span class="sxs-lookup"><span data-stu-id="ca11a-131">$X_2$</span></span> | <span data-ttu-id="ca11a-132">$ \ket{001}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-132">$\ket{001}$</span></span> | <span data-ttu-id="ca11a-133">$ \ket{110}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-133">$\ket{110}$</span></span> |

<span data-ttu-id="ca11a-134">Con el fin de proteger el estado que estamos codificando, es necesario poder distinguir los tres errores entre sí y la identidad $ \boldone $ sin distinción entre $ \ket{\overline{0}} $ y $ \ket{\overline{1}} $.</span><span class="sxs-lookup"><span data-stu-id="ca11a-134">In order to protect the state that we're encoding, we need to be able to distinguish the three errors from each other and from the identity $\boldone$ without distinguishing between $\ket{\overline{0}}$ and $\ket{\overline{1}}$.</span></span>
<span data-ttu-id="ca11a-135">Por ejemplo, si se mide $Z _0 $, se obtiene un resultado diferente para $ \ket{\overline{0}} $ y $ \ket{\overline{1}} $ en el caso de no error, de modo que contrae el estado codificado.</span><span class="sxs-lookup"><span data-stu-id="ca11a-135">For example, if we measure $Z_0$, we get a different result for $\ket{\overline{0}}$ and $\ket{\overline{1}}$ in the no-error case, so that collapses the encoded state.</span></span>
<span data-ttu-id="ca11a-136">Por otro lado, considere la posibilidad de medir $Z _0 Z_1 $, la paridad de los primeros dos bits en cada estado de base de cálculo.</span><span class="sxs-lookup"><span data-stu-id="ca11a-136">On the other hand, consider measuring $Z_0 Z_1$, the parity of the first two bits in each computational basis state.</span></span>
<span data-ttu-id="ca11a-137">Recuerde que cada medida de un operador Pauli comprueba qué eigenvalue se corresponde con el estado que se va a medir, por lo que para cada estado $ \ket{\psi} $ de la tabla anterior, podemos calcular $Z _0 Z_1 \ket{\psi} $ para ver si obtenemos $ \pm\ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="ca11a-137">Recall that each measurement of a Pauli operator checks which eigenvalue  the state being measured corresponds to, so for each state $\ket{\psi}$ in the table above, we can compute $Z_0 Z_1 \ket{\psi}$ to see if we get $\pm\ket{\psi}$.</span></span>
<span data-ttu-id="ca11a-138">Tenga en cuenta que $Z _0 Z_1 \ket{000} = \ket{000}$ y que $Z _0 Z_1 \ket{111} = \ket{111}$, por lo que concluyemos que esta medida hace lo mismo con ambos Estados codificados.</span><span class="sxs-lookup"><span data-stu-id="ca11a-138">Note that $Z_0 Z_1 \ket{000} = \ket{000}$ and that $Z_0 Z_1 \ket{111} = \ket{111}$, so that we conclude that this measurement does the same thing to both encoded states.</span></span>
<span data-ttu-id="ca11a-139">Por otro lado, $Z _0 Z_1 \ket{100} =-\ket{100}$ y $Z _0 Z_1 \ket{011} =-\ket{011}$, por lo que el resultado de la medición de $Z _0 Z_1 $ revela información útil sobre el error que se ha producido.</span><span class="sxs-lookup"><span data-stu-id="ca11a-139">On the other hand, $Z_0 Z_1 \ket{100} = - \ket{100}$ and $Z_0 Z_1 \ket{011} = -\ket{011}$, so the result of measuring $Z_0 Z_1$ reveals useful information about which error occured.</span></span>

<span data-ttu-id="ca11a-140">Para enfatizar esto, se repite la tabla anterior, pero se agregan los resultados de la medición $Z _0 Z_1 $ y $Z _ 1 Z_2 $ en cada fila.</span><span class="sxs-lookup"><span data-stu-id="ca11a-140">To emphasize this, we repeat the table above, but add the results of measuring $Z_0 Z_1$ and $Z_1 Z_2$ on each row.</span></span>
<span data-ttu-id="ca11a-141">Denotamos los resultados de cada medida por el signo del eigenvalue que se observa, ya sea $ + $ o $-$, que corresponde a los valores Q # `Result` de `Zero` y `One`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ca11a-141">We denote the results of each measurement by the sign of the eigenvalue that is observed, either $+$ or $-$, corresponding to the Q# `Result` values of `Zero` and `One`, respectively.</span></span>

| <span data-ttu-id="ca11a-142">Error $E $</span><span class="sxs-lookup"><span data-stu-id="ca11a-142">Error $E$</span></span> | <span data-ttu-id="ca11a-143">$E \ket{\overline{0}} $</span><span class="sxs-lookup"><span data-stu-id="ca11a-143">$E\ket{\overline{0}}$</span></span> | <span data-ttu-id="ca11a-144">$E \ket{\overline{1}} $</span><span class="sxs-lookup"><span data-stu-id="ca11a-144">$E\ket{\overline{1}}$</span></span> | <span data-ttu-id="ca11a-145">Resultado de $Z _0 Z_1 $</span><span class="sxs-lookup"><span data-stu-id="ca11a-145">Result of $Z_0 Z_1$</span></span> | <span data-ttu-id="ca11a-146">Resultado de $Z _ 1 _ Z_2 $</span><span class="sxs-lookup"><span data-stu-id="ca11a-146">Result of $Z_1 Z_2$</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="ca11a-147">$ \boldone $</span><span class="sxs-lookup"><span data-stu-id="ca11a-147">$\boldone$</span></span> | <span data-ttu-id="ca11a-148">$ \ket{000}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-148">$\ket{000}$</span></span> | <span data-ttu-id="ca11a-149">$ \ket{111}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-149">$\ket{111}$</span></span> | $+$ | $+$ |
| <span data-ttu-id="ca11a-150">$X _0 $</span><span class="sxs-lookup"><span data-stu-id="ca11a-150">$X_0$</span></span> | <span data-ttu-id="ca11a-151">$ \ket{100}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-151">$\ket{100}$</span></span> | <span data-ttu-id="ca11a-152">$ \ket{011}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-152">$\ket{011}$</span></span> | $-$ | $+$ |
| <span data-ttu-id="ca11a-153">$X _ 1 _ $</span><span class="sxs-lookup"><span data-stu-id="ca11a-153">$X_1$</span></span> | <span data-ttu-id="ca11a-154">$ \ket{010}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-154">$\ket{010}$</span></span> | <span data-ttu-id="ca11a-155">$ \ket{101}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-155">$\ket{101}$</span></span> | $-$ | $-$ |
| <span data-ttu-id="ca11a-156">$X _2 $</span><span class="sxs-lookup"><span data-stu-id="ca11a-156">$X_2$</span></span> | <span data-ttu-id="ca11a-157">$ \ket{001}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-157">$\ket{001}$</span></span> | <span data-ttu-id="ca11a-158">$ \ket{110}$</span><span class="sxs-lookup"><span data-stu-id="ca11a-158">$\ket{110}$</span></span> | $+$ | $-$ |

<span data-ttu-id="ca11a-159">Por lo tanto, los resultados de las dos medidas determinan de forma exclusiva qué error de volteo de bits se produjo, pero sin revelar ninguna información sobre el estado que hemos codificado.</span><span class="sxs-lookup"><span data-stu-id="ca11a-159">Thus, the results of the two measurements uniquely determines which bit-flip error occured, but without revealing any information about which state we encoded.</span></span>
<span data-ttu-id="ca11a-160">Llamamos a estos resultados como un *síndrome*y hacen referencia al proceso de asignación de un síndrome de vuelta al error que lo causó como *recuperación*.</span><span class="sxs-lookup"><span data-stu-id="ca11a-160">We call these results a *syndrome*, and refer to the process of mapping a syndrome back to the error that caused it as *recovery*.</span></span>
<span data-ttu-id="ca11a-161">En concreto, hacemos hincapié en que la recuperación es un procedimiento de inferencia *clásico* que toma como entrada el síndrome que se produjo y devuelve una receta sobre cómo corregir los errores que se hayan producido.</span><span class="sxs-lookup"><span data-stu-id="ca11a-161">In particular, we emphasize that recovery is a *classical* inference procedure which takes as its input the syndrome which occured, and returns a prescription for how to fix any errors that may have occured.</span></span>

> [!NOTE]
> <span data-ttu-id="ca11a-162">El código de volteo de bits anterior solo puede corregirse frente a errores de volteo de bit único; es decir, una operación de `X` que actúa en un único qubit.</span><span class="sxs-lookup"><span data-stu-id="ca11a-162">The bit-flip code above can only correct against single bit-flip errors; that is, an `X` operation acting on a single qubit.</span></span>
> <span data-ttu-id="ca11a-163">Al aplicar `X` a más de un qubit, se asignará $ \ket{\overline{0}} $ a $ \ket{\overline{1}} $ después de la recuperación.</span><span class="sxs-lookup"><span data-stu-id="ca11a-163">Applying `X` to more than one qubit will map $\ket{\overline{0}}$ to $\ket{\overline{1}}$ following recovery.</span></span>
> <span data-ttu-id="ca11a-164">Del mismo modo, aplicar una operación de volteo de fase `Z` asignará $ \ket{\overline{1}} $ a $-\ket{\overline{1}} $ y, por lo tanto, asignará $ \ket{\overline{+}} $ a $ \ket{\overline{-}} $.</span><span class="sxs-lookup"><span data-stu-id="ca11a-164">Similarly, applying a phase flip operation `Z` will map $\ket{\overline{1}}$ to $-\ket{\overline{1}}$, and hence will map $\ket{\overline{+}}$ to $\ket{\overline{-}}$.</span></span>
> <span data-ttu-id="ca11a-165">En general, se pueden crear códigos para controlar un mayor número de errores y controlar $Z $ errores, así como $X errores $.</span><span class="sxs-lookup"><span data-stu-id="ca11a-165">More generally, codes can be created to handle larger number of errors, and to handle $Z$ errors as well as $X$ errors.</span></span>

<span data-ttu-id="ca11a-166">La información que podemos describir medidas en la corrección de errores de Quantum que actúan de la misma manera en todos los Estados de código es el essense del *estabilizador formalismo*.</span><span class="sxs-lookup"><span data-stu-id="ca11a-166">The insight that we can describe measurements in quantum error correction that act the same way on all code states, is the essense of the *stabilizer formalism*.</span></span>
<span data-ttu-id="ca11a-167">Q # Canon proporciona un marco para describir la codificación y la descodificación de los códigos estabilizadores, y para describir cómo se recupera de los errores.</span><span class="sxs-lookup"><span data-stu-id="ca11a-167">The Q# canon provides a framework for describing encoding into and decoding from stabilizer codes, and for describing how one recovers from errors.</span></span>
<span data-ttu-id="ca11a-168">En esta sección, se describe este marco de trabajo y su aplicación para algunos códigos de corrección de errores de Quantum simples.</span><span class="sxs-lookup"><span data-stu-id="ca11a-168">In this section, we describe this framework and its application to a few simple quantum error-correcting codes.</span></span>

> [!TIP]
> <span data-ttu-id="ca11a-169">Una introducción completa al estabilizador formalismo está fuera del ámbito de esta sección.</span><span class="sxs-lookup"><span data-stu-id="ca11a-169">A full introduction to the stabilizer formalism is beyond the scope of this section.</span></span>
> <span data-ttu-id="ca11a-170">Nos referimos a los lectores interesados en obtener más información sobre [Gottesman 2009](https://arxiv.org/abs/0904.2557).</span><span class="sxs-lookup"><span data-stu-id="ca11a-170">We refer readers interested in learning more to [Gottesman 2009](https://arxiv.org/abs/0904.2557).</span></span>

## <a name="representing-error-correcting-codes-in-q"></a><span data-ttu-id="ca11a-171">Representar códigos de corrección de errores en Q #</span><span class="sxs-lookup"><span data-stu-id="ca11a-171">Representing Error Correcting Codes in Q#</span></span> ##

<span data-ttu-id="ca11a-172">Para ayudar a especificar los códigos de corrección de errores, Q # Canon proporciona varios tipos definidos por el usuario distintos:</span><span class="sxs-lookup"><span data-stu-id="ca11a-172">To help specify error correcting codes, the Q# canon provides several distinct user-defined types:</span></span>

- <span data-ttu-id="ca11a-173"><xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: denota que un registro de qubits debe interpretarse como el bloque de código de un código de corrección de errores.</span><span class="sxs-lookup"><span data-stu-id="ca11a-173"><xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: Denotes that a register of qubits should be interpreted as the code block of an error-correcting code.</span></span>
- <span data-ttu-id="ca11a-174"><xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: denota que una matriz de resultados de medida debe interpretarse como el síndrome medido en un bloque de código.</span><span class="sxs-lookup"><span data-stu-id="ca11a-174"><xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: Denotes that an array of measurement results should be interpreted as the syndrome measured on a code block.</span></span>
- <span data-ttu-id="ca11a-175"><xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`: denota que se debe usar una función *clásica* para interpretar un síndrome y devolver una corrección que se debe aplicar.</span><span class="sxs-lookup"><span data-stu-id="ca11a-175"><xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`: Denotes that a *classical* function should be used to interpret a syndrome and return a correction that should be applied.</span></span>
- <span data-ttu-id="ca11a-176"><xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: denota que una operación toma qubits que representan datos junto con ancilla qubits actualizado para generar un bloque de código con un código de corrección de errores.</span><span class="sxs-lookup"><span data-stu-id="ca11a-176"><xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: Denotes that an operation takes qubits representing data along with fresh ancilla qubits in order to produce a code block of an error-correcting code.</span></span>
- <span data-ttu-id="ca11a-177"><xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: denota que una operación descompone un bloque de código de un error que corrige código en el qubits de datos y el ancilla qubits que se usa para representar la información del síndrome.</span><span class="sxs-lookup"><span data-stu-id="ca11a-177"><xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: Denotes than an operation decomposes a code block of an error correcting code into the data qubits and the ancilla qubits used to represent syndrome information.</span></span>
- <span data-ttu-id="ca11a-178"><xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: denota una operación que debe usarse para extraer información de síndrome de un bloque de código, sin alterar el estado protegido por el código.</span><span class="sxs-lookup"><span data-stu-id="ca11a-178"><xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: Denotes an operation that should be used to extract syndrome information from a code block, without disturbing the state protected by the code.</span></span>

<span data-ttu-id="ca11a-179">Por último, la Canon proporciona el tipo de <xref:microsoft.quantum.errorcorrection.qecc> para recopilar los otros tipos necesarios para definir un código de corrección de errores de Quantum.</span><span class="sxs-lookup"><span data-stu-id="ca11a-179">Finally, the canon provides the <xref:microsoft.quantum.errorcorrection.qecc> type to collect the other types required to define a quantum error-correcting code.</span></span> <span data-ttu-id="ca11a-180">Asociado con cada código Quantum del estabilizador es la longitud del código $n $, el número $k $ de qubits lógicos y la distancia mínima $d $, que a menudo se agrupan juntos en la notación ⟦ $n $, $k $, $d $ ⟧.</span><span class="sxs-lookup"><span data-stu-id="ca11a-180">Associated with each stabilizer quantum code is the code length $n$, the number $k$ of logical qubits, and the minimum distance $d$, often conveniently grouped together in the notation ⟦$n$, $k$, $d$⟧.</span></span> <span data-ttu-id="ca11a-181">Por ejemplo, la función <xref:microsoft.quantum.errorcorrection.bitflipcode> define el código ⟦ 3, 1, 1 ⟧ bit Flip:</span><span class="sxs-lookup"><span data-stu-id="ca11a-181">For example, the <xref:microsoft.quantum.errorcorrection.bitflipcode> function defines the ⟦3, 1, 1⟧ bit flip code:</span></span>

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

<span data-ttu-id="ca11a-182">Observe que el tipo de `QECC` *no incluye una* función de recuperación.</span><span class="sxs-lookup"><span data-stu-id="ca11a-182">Notice that the `QECC` type does *not* include a recovery function.</span></span>
<span data-ttu-id="ca11a-183">Esto nos permite cambiar la función de recuperación que se usa para corregir errores sin cambiar la definición del propio código; Esta capacidad es especialmente útil cuando se incorporan comentarios de medidas de caracterización en el modelo asumido por recuperación.</span><span class="sxs-lookup"><span data-stu-id="ca11a-183">This allows us to change the recovery function that is used in correcting errors without changing the definition of the code itself; this ability is in particular useful when incorporating feedback from characterization measurements into the model assumed by recovery.</span></span>

<span data-ttu-id="ca11a-184">Una vez que se define un código de esta manera, se puede usar la operación <xref:microsoft.quantum.errorcorrection.recover> para recuperarse de errores:</span><span class="sxs-lookup"><span data-stu-id="ca11a-184">Once a code is defined in this way, we can use the <xref:microsoft.quantum.errorcorrection.recover> operation to recover from errors:</span></span>

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

<span data-ttu-id="ca11a-185">Lo exploramos con más detalle en el [ejemplo de código de volteo de bits](https://github.com/Microsoft/Quantum/tree/master/Samples/src/BitFlipCode).</span><span class="sxs-lookup"><span data-stu-id="ca11a-185">We explore this in more detail in the [bit flip code sample](https://github.com/Microsoft/Quantum/tree/master/Samples/src/BitFlipCode).</span></span>

<span data-ttu-id="ca11a-186">Además del código de volteo de bits, se proporciona Q # Canon con implementaciones del [código perfecto de cinco qubit](https://arxiv.org/abs/1305.08)y el [código de siete qubit](https://arxiv.org/abs/quant-ph/9705052), y ambos pueden corregir un error arbitrario de qubit único.</span><span class="sxs-lookup"><span data-stu-id="ca11a-186">Aside from the bit-flip code, the Q# canon is provided with implementations of the [five-qubit perfect code](https://arxiv.org/abs/1305.08), and the [seven-qubit code](https://arxiv.org/abs/quant-ph/9705052), both of which can correct an arbitrary single-qubit error.</span></span>