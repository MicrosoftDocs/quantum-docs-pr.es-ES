---
title: Especificación del esquema Broombridge (versión 0,2)
description: Detalla las especificaciones para el esquema de química Broombridge de Quantum v 0,2 para Microsoft Quantum química Library.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: df7e651b7d32e672c6e83346ff603132bd55c1a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907280"
---
# <a name="broombridge-specification-v02"></a>Especificación de Broombridge v 0,2 #

Las palabras clave "debe", "no debe", "Required", "", "no debe", "no debería", "no debería", "recomendado", "puede" y "opcional" en este documento se deben interpretar como se describe en [RFC 2119](https://tools.ietf.org/html/rfc2119).

Cualquier barra lateral con los títulos "Nota", "información" o "ADVERTENCIA" es informativa.

## <a name="introduction"></a>Introducción ##

Esta sección es informativa.

Los documentos de Broombridge están diseñados para comunicar instancias de problemas de simulación en la química Quantum para su procesamiento mediante la simulación de Quantum y la programación de cadenas.

## <a name="serialization"></a>Serialización ##

Esta sección es normativa.

Un documento de Broombridge debe serializarse como un [documento YAML 1,2](http://yaml.org/spec/) que represente un objeto JSON, tal como se describe en la sección 2,2 de [RFC 4627](https://tools.ietf.org/html/rfc4627) .
El objeto serializado a YAML debe tener una propiedad `"$schema"` cuyo valor sea `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`y debe ser válido de acuerdo con las especificaciones de draft-06 del esquema JSON [[1,2](https://tools.ietf.org/html/draft-wright-json-schema-01) [].](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)

En el resto de esta especificación, "el objeto Broombridge" hará referencia al objeto JSON deserializado de un documento YAML de Broombridge.

A menos que se indique lo contrario explícitamente, los objetos no deben tener propiedades adicionales más allá de las especificadas explícitamente en este documento.

## <a name="additional-definitions"></a>Definiciones adicionales ##

Esta sección es normativa.

### <a name="quantity-objects"></a>Objetos quantity ###

Esta sección es normativa.

Un _objeto quantity_ es un objeto JSON y debe tener una propiedad `units` cuyo valor sea uno de los valores permitidos enumerados en la tabla 1.

Un objeto quantity es un _objeto quantity simple_ si tiene una propiedad única `value` además de su propiedad `units`.
El valor de la propiedad `value` debe ser un número.

Un objeto quantity es un _objeto quantity limitado_ si tiene las propiedades `lower` y `upper` además de su propiedad `units`.
Los valores de las propiedades `lower` y `upper` deben ser números.
Un objeto quantity limitado puede tener una propiedad `value` cuyo valor es un número.

Un objeto quantity es un _objeto de cantidad de matriz dispersa_ si tiene la propiedad `format` y una propiedad `values` además de su propiedad `units`.
El valor de `format` debe ser la cadena `sparse`.
El valor de la propiedad `values` debe ser una matriz.
Cada elemento de `values` debe ser una matriz que represente los índices y el valor de la cantidad de la matriz dispersa.

Los índices de cada elemento de un objeto de cantidad de matriz dispersa deben ser únicos en todo el objeto de cantidad de matriz dispersa.
Si hay un índice con un valor de `0`, un analizador debe tratar el objeto de cantidad de matriz dispersa de forma idéntica a un objeto de cantidad de matriz dispersa en el que ese índice no está presente en absoluto.


Un objeto quantity debe ser

- un objeto quantity simple,
- objeto quantity limitado, o bien
- objeto de cantidad de matriz dispersa.


### <a name="examples"></a>Ejemplos ###

Esta sección es informativa.

Una cantidad simple que representa $1.9844146837\,\mathrm{Ha} $:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Una cantidad limitada que representa una distribución uniforme en el intervalo $ [-7,-6]\,\mathrm{Ha} $:

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Lo siguiente es una cantidad de matriz dispersa con un elemento `[1, 2]` igual a `hello` y un elemento `[3, 4]` igual a `world`:

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>Sección de formato ##

Esta sección es normativa.

El objeto Broombridge debe tener una propiedad `format` cuyo valor sea un objeto JSON con una propiedad denominada `version`.
La propiedad `version` debe tener el valor `"0.2"`.

### <a name="example"></a>Ejemplo ###

Esta sección es informativa.

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a>Sección Descripción del problema ##

Esta sección es normativa.

El objeto Broombridge debe tener una propiedad `problem_description` cuyo valor sea una matriz JSON.
Cada elemento del valor de la propiedad `problem_description` debe ser un objeto JSON que describe un conjunto de enteros, como se describe en el resto de esta sección.
En el resto de esta sección, el término "objeto de Descripción del problema" hará referencia a un elemento en el valor de la propiedad `problem_description` del objeto Broombridge.

Cada objeto de Descripción del problema debe tener una propiedad `metadata` cuyo valor sea un objeto JSON.
El valor de `metadata` puede ser el objeto JSON vacío (es decir, `{}`) o puede contener propiedades adicionales definidas por el implementador.

### <a name="hamiltonian-section"></a>Sección Hamiltonian ###

#### <a name="overview"></a>Información general ####

Esta sección es informativa.

La propiedad `hamiltonian` de cada objeto de Descripción del problema describe el Hamiltonian de un problema de química de Quantum determinado mediante la descripción de sus términos de uno y dos cuerpos como matrices dispersas de números reales.
Los operadores Hamiltonian descritos por cada objeto de Descripción del problema tienen el formato

$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{ij\} a ^\{\dagger\}\_{i, \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} H\_{ijkl} a ^ \dagger\_{i , \sigma} ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $

Aquí $h _ {ijkl} = (ij | KL) $ in Mulliken Convention.

Para mayor claridad, el término de un electrones es

$ $ h_ {ij} = \int {\mathrm d} x \psi ^ *\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $

y el término de dos electrones es

$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).
$$

Como se indicó en la descripción de la [propiedad`basis_set`](#basis-set-object) de cada elemento de la propiedad `integral_sets`, se supone que las funciones de base utilizadas son de valor real.
Esto nos permite usar los siguientes Symmetries entre los términos para comprimir la representación de la Hamiltonian.

$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {JILK} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.
$$


#### <a name="contents"></a>Contenido ####

Esta sección es normativa.

Cada objeto de Descripción del problema debe tener una propiedad `hamiltonian` cuyo valor sea un objeto JSON.
El valor de la propiedad `hamiltonian` se conoce como objeto Hamiltonian y debe tener las propiedades `one_electron_integrals` y `two_electron_integrals` tal y como se describe en el resto de esta sección.

Cada objeto de Descripción del problema debe tener una propiedad `coulomb_repulsion` cuyo valor sea un objeto de cantidad simple.
Cada objeto de Descripción del problema debe tener una propiedad `energy_offet` cuyo valor sea un objeto de cantidad simple.
> Tenga en cuenta Los valores de `coulomb_repulsion` y `energy_offet` agregados juntos capturan el término de identidad de Hamiltonian.

##### <a name="one-electron-integrals-object"></a>Objeto integral de un solo electrones #####

Esta sección es normativa.

La propiedad `one_electron_integrals` del objeto Hamiltonian debe ser una cantidad de matriz dispersa cuyos índices son dos enteros y cuyos valores son números.
Cada término debe tener índices `[i, j]` donde `i >= j`.

> Tenga en cuenta Esto refleja la simetría que $h _ {ij} = h_ {ji} $, que es una consecuencia del hecho de que Hamiltonian es Hermitian.


###### <a name="example"></a>Ejemplo ######

Esta sección es informativa.

La siguiente cantidad de matriz dispersa representa el Hamiltonian $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow}\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1, \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.
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
> Broombridge usa una indización basada en 1.


##### <a name="two-electron-integrals-object"></a>Objeto integral de dos electrones #####

Esta sección es normativa.

La propiedad `two_electron_integrals` del objeto Hamiltonian debe ser una cantidad de matriz dispersa con una propiedad adicional denominada `index_convention`.
Cada elemento del valor de `two_electron_integrals` debe tener cuatro índices.

Cada propiedad `two_electron_integrals` debe tener una propiedad `index_convention`.
El valor de la propiedad `index_convention` debe ser uno de los valores permitidos enumerados en la tabla 1.
Si el valor de `index_convention` es `mulliken`, para cada elemento de la `two_electron_integrals` cantidad de matriz dispersa, un analizador que cargue un documento de Broombridge debe crear una instancia de un término Hamiltonian igual al operador de dos electrones $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, donde $i $, $j $, $k $ y $l $ deben ser enteros de valor al menos 1, y donde $h _ {i, j, k, l} $ es el elemento `[i, j, k, l, h(i, j, k, l)]` de la cantidad de matriz dispersa.

###### <a name="symmetries"></a>Symmetries ######

Esta sección es normativa.

Si la propiedad `index_convention` de un objeto `two_electron_integrals` es igual a `mulliken`, si hay un elemento con índices `[i, j, k, l]`, los siguientes índices no deben estar presentes a menos que sean iguales a `[i, j, k, l]`:

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Dado que la propiedad `index_convention` es un objeto quantity disperso, no se pueden repetir índices en elementos diferentes.
> En concreto, si hay un elemento con índices `[i, j, k, l]` está presente, ningún otro elemento puede tener esos índices.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Ejemplo #######

Esta sección es informativa.

El siguiente objeto especifica Hamiltonian

$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2 , \rho} a\_{3, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2, \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3 , \sigma} a ^ {\dagger}\_{2, \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.
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

### <a name="initial-state-section"></a>Sección de estado inicial ###

Esta sección es normativa.

El objeto `initial_state_suggestion` cuyo valor es una matriz JSON especifica los Estados iniciales de Quantum de interés para el Hamiltonian especificado. Cada elemento del valor de la propiedad `initial_state_suggestion` debe ser un objeto JSON que describe un estado Quantum, como se describe en el resto de esta sección.
En el resto de esta sección, el término "objeto de estado" hará referencia a un elemento en el valor de la propiedad `initial_state_suggestion` del objeto Broombridge.

#### <a name="state-object"></a>Objeto de estado ####

Esta sección es normativa.

Cada objeto de Estado debe tener una propiedad `label` que contenga una cadena. Cada objeto de Estado debe tener una propiedad `method`. El valor de la propiedad `method` debe ser uno de los valores permitidos que se muestran en la tabla 3.
Cada objeto de estado puede tener una propiedad `energy` cuyo valor debe ser un objeto de cantidad simple.

Si el valor de la propiedad `method` es `sparse_multi_configurational`, el objeto de Estado debe tener una propiedad `superposition` que contenga una matriz de Estados base y sus amplitudes no normalizadas.

Por ejemplo, los Estados iniciales $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0,2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0,2 | ^ 2}} \ket{0}, $ $, donde $ \ket{E} $ tiene energía $0,987 \textrm{Ha} $, se representan mediante
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

Si el valor de la propiedad `method` es `unitary_coupled_cluster`, el objeto de Estado debe tener una propiedad `cluster_operator` cuyo valor sea un objeto JSON.
El objeto JSON debe tener una propiedad `reference_state` cuyo valor sea un estado base.
El objeto JSON puede tener una propiedad `one_body_amplitudes` cuyo valor es una matriz de operadores de clúster de un cuerpo y sus amplitudes.
El objeto JSON puede tener una propiedad `two_body_amplitudes` cuyo valor es una matriz de operadores de clúster de dos cuerpos y sus amplitudes.
que contiene una matriz de Estados de base y sus amplitudes no normalizadas.

Por ejemplo, el estado $ $ \ket{\text{Reference}} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0}, $ $

$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{Reference}}, $ $

$ $ T = 0,1 a ^ {\dagger}\_{3, \uparrow}a\_{2, \downarrow} + 0,2 a ^ {\dagger}\_{2, \uparrow}a\_{2, \downarrow}-0,3 a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \downarrow}a\_{3, \uparrow}a\_{2, \downarrow} $ $ se representa mediante
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

#### <a name="basis-set-object"></a>Objeto de conjunto de base ####

Esta sección es normativa.

Cada objeto de Descripción del problema puede tener una propiedad `basis_set`.
Si está presente, el valor de la propiedad `basis_set` debe ser un objeto con dos propiedades, `type` y `name`.

Las funciones de base identificadas por el valor de la propiedad `basis_set` deben ser de valor real.

> [!NOTE]
> La suposición de que todas las funciones base son de valor real se pueden relajar en versiones futuras de esta especificación.

## <a name="tables-and-lists"></a>Tablas y listas ##

### <a name="table-1-allowed-physical-units"></a>Tabla 1. Unidades físicas permitidas ###

Esta sección es normativa.

Cualquier cadena que especifique una unidad debe ser una de las siguientes:

- `hartree`
- `ev`

Los analizadores y productores deben tratar los siguientes objetos de cantidad simple como equivalentes:

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>Tabla 2. Convenciones de índice permitido ###

Esta sección es normativa.

Cualquier cadena que especifique una Convención de índice debe ser una de las siguientes:

- `mulliken`

Esta sección es informativa.

Se pueden introducir convenciones de índice adicionales en versiones futuras de esta especificación.

#### <a name="interpretation-of-index-conventions"></a>Interpretación de las convenciones de índice ####

Esta sección es informativa.

### <a name="table-3-allowed-state-methods"></a>Tabla 3. Métodos de estado permitidos ###

Esta sección es normativa.

Cualquier cadena que especifique un método de Estado debe ser uno de los siguientes:

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

Esta sección es informativa.

Pueden introducirse métodos de estado adicionales en versiones futuras de esta especificación.
