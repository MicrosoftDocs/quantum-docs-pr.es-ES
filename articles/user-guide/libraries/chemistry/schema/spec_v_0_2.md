---
title: Especificación del esquema Broombridge (versión 0,2)
description: Detalla las especificaciones para el esquema de química Broombridge de Quantum v 0,2 para Microsoft Quantum química Library.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: df7e651b7d32e672c6e83346ff603132bd55c1a2
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275859"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="c67b1-103">Especificación de Broombridge v 0,2</span><span class="sxs-lookup"><span data-stu-id="c67b1-103">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="c67b1-104">Las palabras clave "debe", "no debe", "Required", "", "no debe", "no debería", "no debería", "recomendado", "puede" y "opcional" en este documento se deben interpretar como se describe en [RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="c67b1-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="c67b1-105">Cualquier barra lateral con los títulos "Nota", "información" o "ADVERTENCIA" es informativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="c67b1-106">Introducción</span><span class="sxs-lookup"><span data-stu-id="c67b1-106">Introduction</span></span> ##

<span data-ttu-id="c67b1-107">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-107">This section is informative.</span></span>

<span data-ttu-id="c67b1-108">Los documentos de Broombridge están diseñados para comunicar instancias de problemas de simulación en la química Quantum para su procesamiento mediante la simulación de Quantum y la programación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="c67b1-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="c67b1-109">Serialización</span><span class="sxs-lookup"><span data-stu-id="c67b1-109">Serialization</span></span> ##

<span data-ttu-id="c67b1-110">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-110">This section is normative.</span></span>

<span data-ttu-id="c67b1-111">Un documento de Broombridge debe serializarse como un [documento YAML 1,2](http://yaml.org/spec/) que represente un objeto JSON, tal como se describe en la sección 2,2 de [RFC 4627](https://tools.ietf.org/html/rfc4627) .</span><span class="sxs-lookup"><span data-stu-id="c67b1-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="c67b1-112">El objeto serializado a YAML debe tener una propiedad `"$schema"` cuyo valor sea `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` , y debe ser válido de acuerdo con las especificaciones de draft-06 del esquema JSON [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)[[1,2](https://tools.ietf.org/html/draft-wright-json-schema-01)].</span><span class="sxs-lookup"><span data-stu-id="c67b1-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="c67b1-113">En el resto de esta especificación, "el objeto Broombridge" hará referencia al objeto JSON deserializado de un documento YAML de Broombridge.</span><span class="sxs-lookup"><span data-stu-id="c67b1-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="c67b1-114">A menos que se indique lo contrario explícitamente, los objetos no deben tener propiedades adicionales más allá de las especificadas explícitamente en este documento.</span><span class="sxs-lookup"><span data-stu-id="c67b1-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="c67b1-115">Definiciones adicionales</span><span class="sxs-lookup"><span data-stu-id="c67b1-115">Additional Definitions</span></span> ##

<span data-ttu-id="c67b1-116">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="c67b1-117">Objetos quantity</span><span class="sxs-lookup"><span data-stu-id="c67b1-117">Quantity Objects</span></span> ###

<span data-ttu-id="c67b1-118">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-118">This section is normative.</span></span>

<span data-ttu-id="c67b1-119">Un _objeto quantity_ es un objeto JSON y debe tener una propiedad `units` cuyo valor sea uno de los valores permitidos enumerados en la tabla 1.</span><span class="sxs-lookup"><span data-stu-id="c67b1-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="c67b1-120">Un objeto quantity es un _objeto quantity simple_ si tiene una propiedad única además de `value` su `units` propiedad.</span><span class="sxs-lookup"><span data-stu-id="c67b1-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="c67b1-121">El valor de la `value` propiedad debe ser un número.</span><span class="sxs-lookup"><span data-stu-id="c67b1-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="c67b1-122">Un objeto quantity es un _objeto quantity limitado_ si tiene las propiedades `lower` y además de `upper` su `units` propiedad.</span><span class="sxs-lookup"><span data-stu-id="c67b1-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="c67b1-123">Los valores de las `lower` `upper` propiedades y deben ser números.</span><span class="sxs-lookup"><span data-stu-id="c67b1-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="c67b1-124">Un objeto quantity limitado puede tener una propiedad `value` cuyo valor es un número.</span><span class="sxs-lookup"><span data-stu-id="c67b1-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="c67b1-125">Un objeto quantity es un _objeto de cantidad de matriz dispersa_ si tiene la propiedad `format` y una propiedad `values` además de su `units` propiedad.</span><span class="sxs-lookup"><span data-stu-id="c67b1-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="c67b1-126">El valor de `format` debe ser la cadena `sparse` .</span><span class="sxs-lookup"><span data-stu-id="c67b1-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="c67b1-127">El valor de la `values` propiedad debe ser una matriz.</span><span class="sxs-lookup"><span data-stu-id="c67b1-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="c67b1-128">Cada elemento de `values` debe ser una matriz que represente los índices y el valor de la cantidad de la matriz dispersa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="c67b1-129">Los índices de cada elemento de un objeto de cantidad de matriz dispersa deben ser únicos en todo el objeto de cantidad de matriz dispersa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="c67b1-130">Si un índice está presente con un valor de `0` , un analizador debe tratar el objeto de cantidad de matriz dispersa de forma idéntica a un objeto de cantidad de matriz dispersa en el que ese índice no está presente en absoluto.</span><span class="sxs-lookup"><span data-stu-id="c67b1-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="c67b1-131">Un objeto quantity debe ser</span><span class="sxs-lookup"><span data-stu-id="c67b1-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="c67b1-132">un objeto quantity simple,</span><span class="sxs-lookup"><span data-stu-id="c67b1-132">a simple quantity object,</span></span>
- <span data-ttu-id="c67b1-133">objeto quantity limitado, o bien</span><span class="sxs-lookup"><span data-stu-id="c67b1-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="c67b1-134">objeto de cantidad de matriz dispersa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="c67b1-135">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c67b1-135">Examples</span></span> ###

<span data-ttu-id="c67b1-136">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-136">This section is informative.</span></span>

<span data-ttu-id="c67b1-137">Una cantidad simple que representa $1.9844146837 \, \mathrm{ha} $:</span><span class="sxs-lookup"><span data-stu-id="c67b1-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="c67b1-138">Una cantidad limitada que representa una distribución uniforme en el intervalo $ [-7,-6] \, \mathrm{ha} $:</span><span class="sxs-lookup"><span data-stu-id="c67b1-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="c67b1-139">Lo siguiente es una cantidad de matriz dispersa con un elemento `[1, 2]` igual a `hello` y un elemento `[3, 4]` igual a `world` :</span><span class="sxs-lookup"><span data-stu-id="c67b1-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="c67b1-140">Sección de formato</span><span class="sxs-lookup"><span data-stu-id="c67b1-140">Format Section</span></span> ##

<span data-ttu-id="c67b1-141">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-141">This section is normative.</span></span>

<span data-ttu-id="c67b1-142">El objeto Broombridge debe tener una propiedad `format` cuyo valor sea un objeto JSON con una propiedad denominada `version` .</span><span class="sxs-lookup"><span data-stu-id="c67b1-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="c67b1-143">La `version` propiedad debe tener el valor `"0.2"` .</span><span class="sxs-lookup"><span data-stu-id="c67b1-143">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="c67b1-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c67b1-144">Example</span></span> ###

<span data-ttu-id="c67b1-145">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="c67b1-146">Sección Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="c67b1-146">Problem Description Section</span></span> ##

<span data-ttu-id="c67b1-147">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-147">This section is normative.</span></span>

<span data-ttu-id="c67b1-148">El objeto Broombridge debe tener una propiedad `problem_description` cuyo valor sea una matriz JSON.</span><span class="sxs-lookup"><span data-stu-id="c67b1-148">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="c67b1-149">Cada elemento del valor de la `problem_description` propiedad debe ser un objeto JSON que describe un conjunto de enteros, como se describe en el resto de esta sección.</span><span class="sxs-lookup"><span data-stu-id="c67b1-149">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="c67b1-150">En el resto de esta sección, el término "objeto de Descripción del problema" hará referencia a un elemento en el valor de la `problem_description` propiedad del objeto Broombridge.</span><span class="sxs-lookup"><span data-stu-id="c67b1-150">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="c67b1-151">Cada objeto de Descripción del problema debe tener una propiedad `metadata` cuyo valor sea un objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="c67b1-151">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="c67b1-152">El valor de `metadata` puede ser el objeto JSON vacío (es decir, `{}` ) o puede contener propiedades adicionales definidas por el implementador.</span><span class="sxs-lookup"><span data-stu-id="c67b1-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="c67b1-153">Sección Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="c67b1-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="c67b1-154">Información general</span><span class="sxs-lookup"><span data-stu-id="c67b1-154">Overview</span></span> ####

<span data-ttu-id="c67b1-155">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-155">This section is informative.</span></span>

<span data-ttu-id="c67b1-156">La `hamiltonian` propiedad de cada objeto de Descripción del problema describe el Hamiltonian de un problema de química de Quantum determinado al enumerar sus términos de uno y dos cuerpos como matrices dispersas de números reales.</span><span class="sxs-lookup"><span data-stu-id="c67b1-156">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="c67b1-157">Los operadores Hamiltonian descritos por cada objeto de Descripción del problema tienen el formato</span><span class="sxs-lookup"><span data-stu-id="c67b1-157">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="c67b1-158">$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} H \_ \{ \} a ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} H \_ {ijkl} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="c67b1-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="c67b1-159">Aquí $h _ {ijkl} = (ij | KL) $ in Mulliken Convention.</span><span class="sxs-lookup"><span data-stu-id="c67b1-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="c67b1-160">Para mayor claridad, el término de un electrones es</span><span class="sxs-lookup"><span data-stu-id="c67b1-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="c67b1-161">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \* \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {a} \frac{Z \_ a} {| x-x \_ a |}  \right) \psi \_ j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="c67b1-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="c67b1-162">y el término de dos electrones es</span><span class="sxs-lookup"><span data-stu-id="c67b1-162">and the two-electron term is</span></span>

<span data-ttu-id="c67b1-163">$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="c67b1-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="c67b1-164">Como se indicó en la descripción de la [ `basis_set` propiedad](#basis-set-object) de cada elemento de la `integral_sets` propiedad, se supone explícitamente que las funciones de base utilizadas son de valor real.</span><span class="sxs-lookup"><span data-stu-id="c67b1-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="c67b1-165">Esto nos permite usar los siguientes Symmetries entre los términos para comprimir la representación de la Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="c67b1-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="c67b1-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {JILK} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="c67b1-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="c67b1-167">Contenido</span><span class="sxs-lookup"><span data-stu-id="c67b1-167">Contents</span></span> ####

<span data-ttu-id="c67b1-168">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-168">This section is normative.</span></span>

<span data-ttu-id="c67b1-169">Cada objeto de Descripción del problema debe tener una propiedad `hamiltonian` cuyo valor sea un objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="c67b1-169">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="c67b1-170">El valor de la `hamiltonian` propiedad se conoce como objeto Hamiltonian y debe tener las propiedades y, `one_electron_integrals` `two_electron_integrals` tal y como se describe en el resto de esta sección.</span><span class="sxs-lookup"><span data-stu-id="c67b1-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="c67b1-171">Cada objeto de Descripción del problema debe tener una propiedad `coulomb_repulsion` cuyo valor sea un objeto de cantidad simple.</span><span class="sxs-lookup"><span data-stu-id="c67b1-171">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="c67b1-172">Cada objeto de Descripción del problema debe tener una propiedad `energy_offet` cuyo valor sea un objeto de cantidad simple.</span><span class="sxs-lookup"><span data-stu-id="c67b1-172">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="c67b1-173">Tenga en cuenta Los valores de `coulomb_repulsion` y se `energy_offet` agregan conjuntamente capturan el término de identidad de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="c67b1-173">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="c67b1-174">Objeto integral de un solo electrones</span><span class="sxs-lookup"><span data-stu-id="c67b1-174">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="c67b1-175">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-175">This section is normative.</span></span>

<span data-ttu-id="c67b1-176">La `one_electron_integrals` propiedad del objeto HAMILTONIAN debe ser una cantidad de matriz dispersa cuyos índices son dos enteros y cuyos valores son números.</span><span class="sxs-lookup"><span data-stu-id="c67b1-176">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="c67b1-177">Cada término debe tener índices `[i, j]` donde `i >= j` .</span><span class="sxs-lookup"><span data-stu-id="c67b1-177">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="c67b1-178">Tenga en cuenta Esto refleja la simetría que $h _ {ij} = h_ {ji} $, que es una consecuencia del hecho de que Hamiltonian es Hermitian.</span><span class="sxs-lookup"><span data-stu-id="c67b1-178">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="c67b1-179">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c67b1-179">Example</span></span> ######

<span data-ttu-id="c67b1-180">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-180">This section is informative.</span></span>

<span data-ttu-id="c67b1-181">La siguiente cantidad de matriz dispersa representa el Hamiltonian $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (a ^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {2, \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="c67b1-181">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> <span data-ttu-id="c67b1-182">Broombridge usa una indización basada en 1.</span><span class="sxs-lookup"><span data-stu-id="c67b1-182">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="c67b1-183">Objeto integral de dos electrones</span><span class="sxs-lookup"><span data-stu-id="c67b1-183">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="c67b1-184">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-184">This section is normative.</span></span>

<span data-ttu-id="c67b1-185">La `two_electron_integrals` propiedad del objeto HAMILTONIAN debe ser una cantidad de matriz dispersa con una propiedad adicional denominada `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="c67b1-185">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="c67b1-186">Cada elemento del valor de `two_electron_integrals` debe tener cuatro índices.</span><span class="sxs-lookup"><span data-stu-id="c67b1-186">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="c67b1-187">Cada `two_electron_integrals` propiedad debe tener una `index_convention` propiedad.</span><span class="sxs-lookup"><span data-stu-id="c67b1-187">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="c67b1-188">El valor de la `index_convention` propiedad debe ser uno de los valores permitidos enumerados en la tabla 1.</span><span class="sxs-lookup"><span data-stu-id="c67b1-188">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="c67b1-189">Si el valor de `index_convention` es `mulliken` , para cada elemento de la `two_electron_integrals` cantidad de matriz dispersa, un analizador que carga un documento de Broombridge debe crear una instancia de un término Hamiltonian igual al operador de dos electrones $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k A_L $, donde $i $, $j $, $k $ y $l $ deben ser enteros de valor al menos 1, y donde $h _ {i, j, k, l} $ es el elemento `[i, j, k, l, h(i, j, k, l)]` de la cantidad de matriz dispersa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-189">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="c67b1-190">Symmetries</span><span class="sxs-lookup"><span data-stu-id="c67b1-190">Symmetries</span></span> ######

<span data-ttu-id="c67b1-191">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-191">This section is normative.</span></span>

<span data-ttu-id="c67b1-192">Si la `index_convention` propiedad de un `two_electron_integrals` objeto es igual a `mulliken` , si hay un elemento con índices `[i, j, k, l]` , los índices siguientes no deben estar presentes a menos que sean iguales a `[i, j, k, l]` :</span><span class="sxs-lookup"><span data-stu-id="c67b1-192">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="c67b1-193">Dado `index_convention` que la propiedad es un objeto quantity disperso, no se pueden repetir índices en elementos diferentes.</span><span class="sxs-lookup"><span data-stu-id="c67b1-193">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="c67b1-194">En concreto, si un elemento con índices `[i, j, k, l]` está presente, ningún otro elemento puede tener esos índices.</span><span class="sxs-lookup"><span data-stu-id="c67b1-194">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="c67b1-195">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c67b1-195">Example</span></span> #######

<span data-ttu-id="c67b1-196">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-196">This section is informative.</span></span>

<span data-ttu-id="c67b1-197">El siguiente objeto especifica Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="c67b1-197">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="c67b1-198">$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} { \_ 1, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {2, \rho} a \_ {3, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="c67b1-198">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

### <a name="initial-state-section"></a><span data-ttu-id="c67b1-199">Sección de estado inicial</span><span class="sxs-lookup"><span data-stu-id="c67b1-199">Initial State Section</span></span> ###

<span data-ttu-id="c67b1-200">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-200">This section is normative.</span></span>

<span data-ttu-id="c67b1-201">El `initial_state_suggestion` objeto cuyo valor es una matriz JSON especifica los Estados iniciales de Quantum de interés para el Hamiltonian especificado.</span><span class="sxs-lookup"><span data-stu-id="c67b1-201">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="c67b1-202">Cada elemento del valor de la `initial_state_suggestion` propiedad debe ser un objeto JSON que describe un estado de Quantum, tal y como se describe en el resto de esta sección.</span><span class="sxs-lookup"><span data-stu-id="c67b1-202">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="c67b1-203">En el resto de esta sección, el término "objeto de estado" hará referencia a un elemento en el valor de la `initial_state_suggestion` propiedad del objeto Broombridge.</span><span class="sxs-lookup"><span data-stu-id="c67b1-203">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="c67b1-204">Objeto de estado</span><span class="sxs-lookup"><span data-stu-id="c67b1-204">State object</span></span> ####

<span data-ttu-id="c67b1-205">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-205">This section is normative.</span></span>

<span data-ttu-id="c67b1-206">Cada objeto de Estado debe tener una `label` propiedad que contenga una cadena.</span><span class="sxs-lookup"><span data-stu-id="c67b1-206">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="c67b1-207">Cada objeto de Estado debe tener una `method` propiedad.</span><span class="sxs-lookup"><span data-stu-id="c67b1-207">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="c67b1-208">El valor de la `method` propiedad debe ser uno de los valores permitidos que se muestran en la tabla 3.</span><span class="sxs-lookup"><span data-stu-id="c67b1-208">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="c67b1-209">Cada objeto de estado puede tener una propiedad `energy` cuyo valor debe ser un objeto de cantidad simple.</span><span class="sxs-lookup"><span data-stu-id="c67b1-209">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="c67b1-210">Si el valor de la `method` propiedad es `sparse_multi_configurational` , el objeto de Estado debe tener una `superposition` propiedad que contenga una matriz de Estados de base y sus amplitudes no normalizadas.</span><span class="sxs-lookup"><span data-stu-id="c67b1-210">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="c67b1-211">Por ejemplo, los Estados iniciales $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0,2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0,2 | ^ 2}} \ket {0} , $ $ donde $ \ket{E} $ tiene la energía $0,987 \textrm{ha} $, se representan mediante</span><span class="sxs-lookup"><span data-stu-id="c67b1-211">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

<span data-ttu-id="c67b1-212">Si el valor de la `method` propiedad es `unitary_coupled_cluster` , el objeto de Estado debe tener una `cluster_operator` propiedad cuyo valor sea un objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="c67b1-212">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="c67b1-213">El objeto JSON debe tener una `reference_state` propiedad cuyo valor sea un estado base.</span><span class="sxs-lookup"><span data-stu-id="c67b1-213">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="c67b1-214">El objeto JSON puede tener una `one_body_amplitudes` propiedad cuyo valor es una matriz de operadores de clúster de un cuerpo y sus amplitudes.</span><span class="sxs-lookup"><span data-stu-id="c67b1-214">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="c67b1-215">El objeto JSON puede tener una `two_body_amplitudes` propiedad cuyo valor es una matriz de operadores de clúster de dos cuerpos y sus amplitudes.</span><span class="sxs-lookup"><span data-stu-id="c67b1-215">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="c67b1-216">que contiene una matriz de Estados de base y sus amplitudes no normalizadas.</span><span class="sxs-lookup"><span data-stu-id="c67b1-216">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="c67b1-217">Por ejemplo, el estado $ $ \ket{\text{Reference}} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} , $ $</span><span class="sxs-lookup"><span data-stu-id="c67b1-217">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="c67b1-218">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{Reference}}, $ $</span><span class="sxs-lookup"><span data-stu-id="c67b1-218">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="c67b1-219">$ $ T = 0,1 a ^ {\dagger} \_ {3, \uparrow}a \_ {2, \downarrow} + 0,2 a ^ {\dagger} \_ {2, \uparrow}a \_ {2, \downarrow}-0,3 a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \downarrow}a \_ {3, \uparrow}a \_ {2, \downarrow} $ $ se representa mediante</span><span class="sxs-lookup"><span data-stu-id="c67b1-219">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="c67b1-220">Objeto de conjunto de base</span><span class="sxs-lookup"><span data-stu-id="c67b1-220">Basis Set Object</span></span> ####

<span data-ttu-id="c67b1-221">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-221">This section is normative.</span></span>

<span data-ttu-id="c67b1-222">Cada objeto de Descripción del problema puede tener una `basis_set` propiedad.</span><span class="sxs-lookup"><span data-stu-id="c67b1-222">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="c67b1-223">Si está presente, el valor de la `basis_set` propiedad debe ser un objeto con dos propiedades, `type` y `name` .</span><span class="sxs-lookup"><span data-stu-id="c67b1-223">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="c67b1-224">Las funciones de base identificadas por el valor de la `basis_set` propiedad deben ser de valor real.</span><span class="sxs-lookup"><span data-stu-id="c67b1-224">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="c67b1-225">La suposición de que todas las funciones base son de valor real se pueden relajar en versiones futuras de esta especificación.</span><span class="sxs-lookup"><span data-stu-id="c67b1-225">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="c67b1-226">Tablas y listas</span><span class="sxs-lookup"><span data-stu-id="c67b1-226">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="c67b1-227">Tabla 1.</span><span class="sxs-lookup"><span data-stu-id="c67b1-227">Table 1.</span></span> <span data-ttu-id="c67b1-228">Unidades físicas permitidas</span><span class="sxs-lookup"><span data-stu-id="c67b1-228">Allowed Physical Units</span></span> ###

<span data-ttu-id="c67b1-229">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-229">This section is normative.</span></span>

<span data-ttu-id="c67b1-230">Cualquier cadena que especifique una unidad debe ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c67b1-230">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="c67b1-231">Los analizadores y productores deben tratar los siguientes objetos de cantidad simple como equivalentes:</span><span class="sxs-lookup"><span data-stu-id="c67b1-231">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="c67b1-232">Tabla 2.</span><span class="sxs-lookup"><span data-stu-id="c67b1-232">Table 2.</span></span> <span data-ttu-id="c67b1-233">Convenciones de índice permitido</span><span class="sxs-lookup"><span data-stu-id="c67b1-233">Allowed Index Conventions</span></span> ###

<span data-ttu-id="c67b1-234">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-234">This section is normative.</span></span>

<span data-ttu-id="c67b1-235">Cualquier cadena que especifique una Convención de índice debe ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c67b1-235">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="c67b1-236">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-236">This section is informative.</span></span>

<span data-ttu-id="c67b1-237">Se pueden introducir convenciones de índice adicionales en versiones futuras de esta especificación.</span><span class="sxs-lookup"><span data-stu-id="c67b1-237">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="c67b1-238">Interpretación de las convenciones de índice</span><span class="sxs-lookup"><span data-stu-id="c67b1-238">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="c67b1-239">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-239">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="c67b1-240">Tabla 3.</span><span class="sxs-lookup"><span data-stu-id="c67b1-240">Table 3.</span></span> <span data-ttu-id="c67b1-241">Métodos de estado permitidos</span><span class="sxs-lookup"><span data-stu-id="c67b1-241">Allowed State methods</span></span> ###

<span data-ttu-id="c67b1-242">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-242">This section is normative.</span></span>

<span data-ttu-id="c67b1-243">Cualquier cadena que especifique un método de Estado debe ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c67b1-243">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="c67b1-244">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="c67b1-244">This section is informative.</span></span>

<span data-ttu-id="c67b1-245">Pueden introducirse métodos de estado adicionales en versiones futuras de esta especificación.</span><span class="sxs-lookup"><span data-stu-id="c67b1-245">Additional state methods may be introduced in future versions of this specification.</span></span>
