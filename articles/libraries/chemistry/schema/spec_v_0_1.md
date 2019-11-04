---
title: Especificación del esquema Broombridge
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: a950e04d44e5de8091b034214258d2c2fa663f58
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185365"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="a3c21-102">Especificación de Broombridge v 0.1</span><span class="sxs-lookup"><span data-stu-id="a3c21-102">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="a3c21-103">Las palabras clave "debe", "no debe", "Required", "", "no debe", "no debería", "no debería", "recomendado", "puede" y "opcional" en este documento se deben interpretar como se describe en [RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="a3c21-103">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="a3c21-104">Cualquier barra lateral con los títulos "Nota", "información" o "ADVERTENCIA" es informativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-104">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="a3c21-105">Presentación</span><span class="sxs-lookup"><span data-stu-id="a3c21-105">Introduction</span></span> ##

<span data-ttu-id="a3c21-106">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-106">This section is informative.</span></span>

<span data-ttu-id="a3c21-107">Los documentos de Broombridge están diseñados para comunicar instancias de problemas de simulación en la química Quantum para su procesamiento mediante la simulación de Quantum y la programación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="a3c21-107">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="a3c21-108">Serialización</span><span class="sxs-lookup"><span data-stu-id="a3c21-108">Serialization</span></span> ##

<span data-ttu-id="a3c21-109">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-109">This section is normative.</span></span>

<span data-ttu-id="a3c21-110">Un documento de Broombridge debe serializarse como un [documento YAML 1,2](http://yaml.org/spec/) que represente un objeto JSON, tal como se describe en la sección 2,2 de [RFC 4627](https://tools.ietf.org/html/rfc4627) .</span><span class="sxs-lookup"><span data-stu-id="a3c21-110">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="a3c21-111">El objeto serializado a YAML debe tener una propiedad `"$schema"` cuyo valor sea `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`y debe ser válido de acuerdo con las especificaciones de draft-06 del esquema JSON [[1,2](https://tools.ietf.org/html/draft-wright-json-schema-01) [].](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)</span><span class="sxs-lookup"><span data-stu-id="a3c21-111">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="a3c21-112">En el resto de esta especificación, "el objeto Broombridge" hará referencia al objeto JSON deserializado de un documento YAML de Broombridge.</span><span class="sxs-lookup"><span data-stu-id="a3c21-112">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="a3c21-113">A menos que se indique lo contrario explícitamente, los objetos no deben tener propiedades adicionales más allá de las especificadas explícitamente en este documento.</span><span class="sxs-lookup"><span data-stu-id="a3c21-113">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="a3c21-114">Otras definiciones</span><span class="sxs-lookup"><span data-stu-id="a3c21-114">Additional Definitions</span></span> ##

<span data-ttu-id="a3c21-115">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-115">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="a3c21-116">Objetos quantity</span><span class="sxs-lookup"><span data-stu-id="a3c21-116">Quantity Objects</span></span> ###

<span data-ttu-id="a3c21-117">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-117">This section is normative.</span></span>

<span data-ttu-id="a3c21-118">Un _objeto quantity_ es un objeto JSON y debe tener una propiedad `units` cuyo valor sea uno de los valores permitidos enumerados en la tabla 1.</span><span class="sxs-lookup"><span data-stu-id="a3c21-118">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="a3c21-119">Un objeto quantity es un _objeto quantity simple_ si tiene una propiedad única `value` además de su propiedad `units`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-119">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="a3c21-120">El valor de la propiedad `value` debe ser un número.</span><span class="sxs-lookup"><span data-stu-id="a3c21-120">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="a3c21-121">Un objeto quantity es un _objeto quantity limitado_ si tiene las propiedades `lower` y `upper` además de su propiedad `units`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-121">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="a3c21-122">Los valores de las propiedades `lower` y `upper` deben ser números.</span><span class="sxs-lookup"><span data-stu-id="a3c21-122">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="a3c21-123">Un objeto quantity limitado puede tener una propiedad `value` cuyo valor es un número.</span><span class="sxs-lookup"><span data-stu-id="a3c21-123">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="a3c21-124">Un objeto quantity es un _objeto de cantidad de matriz dispersa_ si tiene la propiedad `format` y una propiedad `values` además de su propiedad `units`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-124">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="a3c21-125">El valor de `format` debe ser la cadena `sparse`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-125">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="a3c21-126">El valor de la propiedad `values` debe ser una matriz.</span><span class="sxs-lookup"><span data-stu-id="a3c21-126">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="a3c21-127">Cada elemento de `values` debe ser una matriz que represente los índices y el valor de la cantidad de la matriz dispersa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-127">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="a3c21-128">Los índices de cada elemento de un objeto de cantidad de matriz dispersa deben ser únicos en todo el objeto de cantidad de matriz dispersa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-128">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="a3c21-129">Si hay un índice con un valor de `0`, un analizador debe tratar el objeto de cantidad de matriz dispersa de forma idéntica a un objeto de cantidad de matriz dispersa en el que ese índice no está presente en absoluto.</span><span class="sxs-lookup"><span data-stu-id="a3c21-129">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="a3c21-130">Un objeto quantity debe ser</span><span class="sxs-lookup"><span data-stu-id="a3c21-130">A quantity object MUST either be</span></span>

- <span data-ttu-id="a3c21-131">un objeto quantity simple,</span><span class="sxs-lookup"><span data-stu-id="a3c21-131">a simple quantity object,</span></span>
- <span data-ttu-id="a3c21-132">objeto quantity limitado, o bien</span><span class="sxs-lookup"><span data-stu-id="a3c21-132">a bounded quantity object, or</span></span>
- <span data-ttu-id="a3c21-133">objeto de cantidad de matriz dispersa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-133">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="a3c21-134">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a3c21-134">Examples</span></span> ###

<span data-ttu-id="a3c21-135">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-135">This section is informative.</span></span>

<span data-ttu-id="a3c21-136">Una cantidad simple que representa $1.9844146837\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="a3c21-136">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="a3c21-137">Una cantidad limitada que representa una distribución uniforme en el intervalo $ [-7,-6]\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="a3c21-137">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="a3c21-138">Lo siguiente es una cantidad de matriz dispersa con un elemento `[1, 2]` igual a `hello` y un elemento `[3, 4]` igual a `world`:</span><span class="sxs-lookup"><span data-stu-id="a3c21-138">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="a3c21-139">Sección de formato</span><span class="sxs-lookup"><span data-stu-id="a3c21-139">Format Section</span></span> ##

<span data-ttu-id="a3c21-140">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-140">This section is normative.</span></span>

<span data-ttu-id="a3c21-141">El objeto Broombridge debe tener una propiedad `format` cuyo valor sea un objeto JSON con una propiedad denominada `version`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-141">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="a3c21-142">La propiedad `version` debe tener el valor `"0.1"`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-142">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="a3c21-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3c21-143">Example</span></span> ###

<span data-ttu-id="a3c21-144">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-144">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="a3c21-145">Sección de conjuntos enteros</span><span class="sxs-lookup"><span data-stu-id="a3c21-145">Integral Sets Section</span></span> ##

<span data-ttu-id="a3c21-146">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-146">This section is normative.</span></span>

<span data-ttu-id="a3c21-147">El objeto Broombridge debe tener una propiedad `integral_sets` cuyo valor sea una matriz JSON.</span><span class="sxs-lookup"><span data-stu-id="a3c21-147">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="a3c21-148">Cada elemento del valor de la propiedad `integral_sets` debe ser un objeto JSON que describe un conjunto de enteros, como se describe en el resto de esta sección.</span><span class="sxs-lookup"><span data-stu-id="a3c21-148">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="a3c21-149">En el resto de esta sección, el término "objeto de conjunto entero" hará referencia a un elemento en el valor de la propiedad `integral_sets` del objeto Broombridge.</span><span class="sxs-lookup"><span data-stu-id="a3c21-149">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="a3c21-150">Cada objeto de conjunto entero debe tener una propiedad `metadata` cuyo valor sea un objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="a3c21-150">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="a3c21-151">El valor de `metadata` puede ser el objeto JSON vacío (es decir, `{}`) o puede contener propiedades adicionales definidas por el implementador.</span><span class="sxs-lookup"><span data-stu-id="a3c21-151">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="a3c21-152">Sección Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="a3c21-152">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="a3c21-153">Información general</span><span class="sxs-lookup"><span data-stu-id="a3c21-153">Overview</span></span> ####

<span data-ttu-id="a3c21-154">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-154">This section is informative.</span></span>

<span data-ttu-id="a3c21-155">La propiedad `hamiltonian` de cada objeto de conjunto entero describe el Hamiltonian de un problema de química de Quantum determinado enumerando sus términos de uno y dos cuerpos como matrices dispersas de números reales.</span><span class="sxs-lookup"><span data-stu-id="a3c21-155">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="a3c21-156">Los operadores Hamiltonian descritos por cada objeto de conjunto entero tienen el formato</span><span class="sxs-lookup"><span data-stu-id="a3c21-156">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="a3c21-157">$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{ij\} a ^\{\dagger\}\_{i , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{ijkl} a ^ \dagger\_{i , \sigma} ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="a3c21-157">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="a3c21-158">Aquí $h _ {ijkl} = (ij | KL) $ in Mulliken Convention.</span><span class="sxs-lookup"><span data-stu-id="a3c21-158">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="a3c21-159">Para mayor claridad, el término de un electrones es</span><span class="sxs-lookup"><span data-stu-id="a3c21-159">For clarity, the one-electron term is</span></span>

<span data-ttu-id="a3c21-160">$ $ H_ {ij} = \int {\mathrm d} x \psi ^ \*\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="a3c21-160">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="a3c21-161">y el término de dos electrones es</span><span class="sxs-lookup"><span data-stu-id="a3c21-161">and the two-electron term is</span></span>

<span data-ttu-id="a3c21-162">$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).</span><span class="sxs-lookup"><span data-stu-id="a3c21-162">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="a3c21-163">Como se indicó en la descripción de la [propiedad`basis_set`](#basis-set-object) de cada elemento de la propiedad `integral_sets`, se supone que las funciones de base utilizadas son de valor real.</span><span class="sxs-lookup"><span data-stu-id="a3c21-163">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="a3c21-164">Esto nos permite usar los siguientes Symmetries entre los términos para comprimir la representación de la Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="a3c21-164">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="a3c21-165">$ $ H_ {ijkl} = H_ {ijlk} = H_ {jikl} = H_ {JILK} = H_ {klij} = H_ {klji} = H_ {lkij} = H_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="a3c21-165">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="a3c21-166">Contenido</span><span class="sxs-lookup"><span data-stu-id="a3c21-166">Contents</span></span> ####

<span data-ttu-id="a3c21-167">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-167">This section is normative.</span></span>

<span data-ttu-id="a3c21-168">Cada conjunto entero debe tener una propiedad `hamiltonian` cuyo valor sea un objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="a3c21-168">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="a3c21-169">El valor de la propiedad `hamiltonian` se conoce como objeto Hamiltonian y debe tener las propiedades `one_electron_integrals` y `two_electron_integrals` tal y como se describe en el resto de esta sección.</span><span class="sxs-lookup"><span data-stu-id="a3c21-169">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="a3c21-170">Un objeto Hamiltonian también puede tener una propiedad `particle_hole_representation`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-170">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="a3c21-171">Si está presente, el valor de `particle_hole_representation` debe seguir el formato descrito en el resto de esta sección.</span><span class="sxs-lookup"><span data-stu-id="a3c21-171">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="a3c21-172">Objeto integral de un solo electrones</span><span class="sxs-lookup"><span data-stu-id="a3c21-172">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="a3c21-173">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-173">This section is normative.</span></span>

<span data-ttu-id="a3c21-174">La propiedad `one_electron_integrals` del objeto Hamiltonian debe ser una cantidad de matriz dispersa cuyos índices son dos enteros y cuyos valores son números.</span><span class="sxs-lookup"><span data-stu-id="a3c21-174">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="a3c21-175">Cada término debe tener índices `[i, j]` donde `i >= j`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-175">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="a3c21-176">Tenga en cuenta Esto refleja la simetría que $h _ {ij} = H_ {ji} $, que es una consecuencia del hecho de que Hamiltonian es Hermitian.</span><span class="sxs-lookup"><span data-stu-id="a3c21-176">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="a3c21-177">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3c21-177">Example</span></span> ######

<span data-ttu-id="a3c21-178">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-178">This section is informative.</span></span>

<span data-ttu-id="a3c21-179">La siguiente cantidad de matriz dispersa representa el Hamiltonian $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1 , \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="a3c21-179">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="a3c21-180">Broombridge usa una indización basada en 1.</span><span class="sxs-lookup"><span data-stu-id="a3c21-180">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="a3c21-181">Objeto integral de dos electrones</span><span class="sxs-lookup"><span data-stu-id="a3c21-181">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="a3c21-182">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-182">This section is normative.</span></span>

<span data-ttu-id="a3c21-183">La propiedad `two_electron_integrals` del objeto Hamiltonian debe ser una cantidad de matriz dispersa con una propiedad adicional denominada `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-183">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="a3c21-184">Cada elemento del valor de `two_electron_integrals` debe tener cuatro índices.</span><span class="sxs-lookup"><span data-stu-id="a3c21-184">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="a3c21-185">Cada propiedad `two_electron_integrals` debe tener una propiedad `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-185">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="a3c21-186">El valor de la propiedad `index_convention` debe ser uno de los valores permitidos enumerados en la tabla 1.</span><span class="sxs-lookup"><span data-stu-id="a3c21-186">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="a3c21-187">Si el valor de `index_convention` es `mulliken`, para cada elemento de la `two_electron_integrals` cantidad de matriz dispersa, un analizador que cargue un documento de Broombridge debe crear una instancia de un término Hamiltonian igual al operador de dos electrones $h _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k A_L $ , donde $i $, $j $, $k $ y $l $ deben ser enteros en el intervalo inclusivo comprendido entre 1 y el número de electrones especificado por la propiedad `n_electrons` del objeto de conjunto entero, y donde $h _ {i, j, k, l} $ es el elemento `[i, j, k, l, h(i, j, k, l)]` de la cantidad de matriz dispersa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-187">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="a3c21-188">Symmetries</span><span class="sxs-lookup"><span data-stu-id="a3c21-188">Symmetries</span></span> ######

<span data-ttu-id="a3c21-189">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-189">This section is normative.</span></span>

<span data-ttu-id="a3c21-190">Si la propiedad `index_convention` de un objeto `two_electron_integrals` es igual a `mulliken`, si hay un elemento con índices `[i, j, k, l]`, los siguientes índices no deben estar presentes a menos que sean iguales a `[i, j, k, l]`:</span><span class="sxs-lookup"><span data-stu-id="a3c21-190">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="a3c21-191">Dado que la propiedad `index_convention` es un objeto quantity disperso, no se pueden repetir índices en elementos diferentes.</span><span class="sxs-lookup"><span data-stu-id="a3c21-191">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="a3c21-192">En concreto, si hay un elemento con índices `[i, j, k, l]` está presente, ningún otro elemento puede tener esos índices.</span><span class="sxs-lookup"><span data-stu-id="a3c21-192">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="a3c21-193">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3c21-193">Example</span></span> #######

<span data-ttu-id="a3c21-194">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-194">This section is informative.</span></span>

<span data-ttu-id="a3c21-195">El siguiente objeto especifica Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="a3c21-195">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="a3c21-196">$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6 , \sigma} ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2 , \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2 , \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="a3c21-196">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="a3c21-197">Partícula: objeto de representación de taladro</span><span class="sxs-lookup"><span data-stu-id="a3c21-197">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="a3c21-198">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-198">This section is normative.</span></span>

<span data-ttu-id="a3c21-199">El objeto de representación de partícula-agujero especifica que los enteros almacenados se definen con respecto a la representación de taladros de partículas, donde los operadores de creación y Annihilation describen las desplazamientos fuera del estado de referencia usado, como un Hartree: Estado de Fock.</span><span class="sxs-lookup"><span data-stu-id="a3c21-199">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="a3c21-200">El objeto es opcional.</span><span class="sxs-lookup"><span data-stu-id="a3c21-200">The object is OPTIONAL.</span></span>
<span data-ttu-id="a3c21-201">Si no se especifica el objeto, el Hamiltonian se interpretará como no dado en la representación del agujero de partículas.</span><span class="sxs-lookup"><span data-stu-id="a3c21-201">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="a3c21-202">Si está presente, el valor de `particle_hole_representation` debe ser un objeto de cantidad de matriz dispersa cuyos índices son de cuatro enteros y cuyos valores son un número y una cadena.</span><span class="sxs-lookup"><span data-stu-id="a3c21-202">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="a3c21-203">La parte de la cadena del valor de cada elemento debe contener solo los caracteres `'+'` y `'-'` que especifica si un factor determinado en el término es un operador de creación o de Annihilation en la representación de partícula-agujero.</span><span class="sxs-lookup"><span data-stu-id="a3c21-203">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="a3c21-204">Por ejemplo `"-+++"` coresponden a un hueco que se crea en el sitio $i $ y a las partículas que se crean en sitios $j, k $ y $l $.</span><span class="sxs-lookup"><span data-stu-id="a3c21-204">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="a3c21-205">Como el valor de la `particle_hole_representation` es un objeto de cantidad de matriz dispersa, se deben especificar las propiedades `unit` y `format`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-205">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="a3c21-206">Las unidades aceptables se incluyen en la tabla 1.</span><span class="sxs-lookup"><span data-stu-id="a3c21-206">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="a3c21-207">La propiedad `format` es obligatoria e indica si los coeficientes de Hamiltonian se especifican como una matriz densa o dispersa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-207">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="a3c21-208">En la versión actual, solo se admiten matrices dispersas, con la interpretación de que todos los elementos no especificados son $0 $, pero las versiones futuras pueden agregar compatibilidad con valores adicionales de la propiedad `format`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-208">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="a3c21-209">Sección de estado inicial</span><span class="sxs-lookup"><span data-stu-id="a3c21-209">Initial State Section</span></span> ###

<span data-ttu-id="a3c21-210">El objeto initial_state_suggestion especifica los Estados iniciales de Quantum de interés para el Hamiltonian especificado.</span><span class="sxs-lookup"><span data-stu-id="a3c21-210">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="a3c21-211">Este objeto debe ser una matriz de objetos JSON `state`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-211">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="a3c21-212">Objeto de estado</span><span class="sxs-lookup"><span data-stu-id="a3c21-212">State object</span></span> ####

<span data-ttu-id="a3c21-213">Cada Estado representa una superposición de órbitas ocupadas.</span><span class="sxs-lookup"><span data-stu-id="a3c21-213">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="a3c21-214">Cada objeto de Estado debe tener una propiedad `label` que contenga una cadena.</span><span class="sxs-lookup"><span data-stu-id="a3c21-214">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="a3c21-215">Cada objeto de Estado debe tener una propiedad `superposition` que contenga una matriz de Estados de base y sus amplitudes no normalizadas.</span><span class="sxs-lookup"><span data-stu-id="a3c21-215">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="a3c21-216">Por ejemplo, los Estados iniciales $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0,2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0,2 | ^ 2}} \ket{0} $ $ representado por</span><span class="sxs-lookup"><span data-stu-id="a3c21-216">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="a3c21-217">Objeto de conjunto de base</span><span class="sxs-lookup"><span data-stu-id="a3c21-217">Basis Set Object</span></span> ####

<span data-ttu-id="a3c21-218">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-218">This section is normative.</span></span>

<span data-ttu-id="a3c21-219">Cada objeto de conjunto entero puede tener una propiedad `basis_set`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-219">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="a3c21-220">Si está presente, el valor de la propiedad `basis_set` debe ser un objeto con dos propiedades, `type` y `name`.</span><span class="sxs-lookup"><span data-stu-id="a3c21-220">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="a3c21-221">Las funciones de base identificadas por el valor de la propiedad `basis_set` deben ser de valor real.</span><span class="sxs-lookup"><span data-stu-id="a3c21-221">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="a3c21-222">La suposición de que todas las funciones base son de valor real se pueden relajar en versiones futuras de esta especificación.</span><span class="sxs-lookup"><span data-stu-id="a3c21-222">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="a3c21-223">Tablas y listas</span><span class="sxs-lookup"><span data-stu-id="a3c21-223">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="a3c21-224">Tabla 1.</span><span class="sxs-lookup"><span data-stu-id="a3c21-224">Table 1.</span></span> <span data-ttu-id="a3c21-225">Unidades físicas permitidas</span><span class="sxs-lookup"><span data-stu-id="a3c21-225">Allowed Physical Units</span></span> ###

<span data-ttu-id="a3c21-226">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-226">This section is normative.</span></span>

<span data-ttu-id="a3c21-227">Cualquier cadena que especifique una unidad debe ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3c21-227">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="a3c21-228">Los analizadores y productores deben tratar los siguientes objetos de cantidad simple como equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a3c21-228">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="a3c21-229">Tabla 2.</span><span class="sxs-lookup"><span data-stu-id="a3c21-229">Table 2.</span></span> <span data-ttu-id="a3c21-230">Convenciones de índice permitido</span><span class="sxs-lookup"><span data-stu-id="a3c21-230">Allowed Index Conventions</span></span> ###

<span data-ttu-id="a3c21-231">Esta sección es normativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-231">This section is normative.</span></span>

<span data-ttu-id="a3c21-232">Cualquier cadena que especifique una Convención de índice debe ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3c21-232">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="a3c21-233">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-233">This section is informative.</span></span>

<span data-ttu-id="a3c21-234">Se pueden introducir convenciones de índice adicionales en versiones futuras de esta especificación.</span><span class="sxs-lookup"><span data-stu-id="a3c21-234">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="a3c21-235">Interpretación de las convenciones de índice</span><span class="sxs-lookup"><span data-stu-id="a3c21-235">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="a3c21-236">Esta sección es informativa.</span><span class="sxs-lookup"><span data-stu-id="a3c21-236">This section is informative.</span></span>
