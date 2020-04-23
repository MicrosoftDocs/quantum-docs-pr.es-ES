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
# <a name="putting-it-all-together-teleportation"></a>Putting It All Together: Teletransportation #
Volvamos al ejemplo del circuito de teletransportación definido en [Circuitos Cuánticos.](xref:microsoft.quantum.concepts.circuits) Vamos a usar esto para ilustrar los conceptos que hemos aprendido hasta ahora. A continuación se proporciona una explicación de la teletransportación cuántica para aquellos que no están familiarizados con la teoría, seguido de un tutorial de la implementación de código en Q. 

## <a name="quantum-teleportation-theory"></a>Teletransportación cuántica: Teoría
La teletransportación cuántica es una técnica para enviar un estado cuántico desconocido (que nos referiremos como el __'mensaje')__ de un qubit en una ubicación a un qubit en otra ubicación (nos referiremos a estos qubits como __'aquí'__ y '__allí__', respectivamente). Podemos representar nuestro __mensaje__ como un vector usando la notación Dirac: 

$$ á ket,psi, á alpha, ket{0} +{1} ábeta, $$

El estado del __mensaje__ qubit es desconocido para nosotros, ya que no sabemos los valores de $-alpha$ y $-beta$.

### <a name="step-1-create-an-entangled-state"></a>Paso 1: Crear un estado enredado
Para enviar el __mensaje__ necesitamos que el qubit __aquí__ se enrede con el qubit __allí__. Esto se logra mediante la aplicación de una puerta Hadamard, seguido de una puerta CNOT. Echemos un vistazo a las matemáticas detrás de estas operaciones de la puerta.

Comenzaremos con los qubits __aquí__ y __allá__ {0}tanto en el estado $-ket $. Después de enredar estos qubits, se encuentran en el estado:

$$ á ket,phi,+ á{1}á frac sqrt{2}('ket{00} {11}+ 'ket' ) '$

### <a name="step-2-send-the-message"></a>Paso 2: Enviar el mensaje
Para enviar el __mensaje__ primero aplicamos una puerta CNOT con el __mensaje__ qubit y __aquí__ qubit como entradas (el __mensaje__ qubit es el control y el __qubit aquí__ es el qubit objetivo, en este caso). Este estado de entrada se puede escribir:

$$ á ket, psi, ket, phi, etc., á{0} ('alpha''{1}''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''{1}{2}{00} {11}

Esto se expande a:

$$ .ket, psi, ket, phi, phi, etc., etc. ,frac, alpha, sqrt,{2}ket , etc.{000} {2}{011} {2}{100} {2}{111}

Como recordatorio, la puerta CNOT voltea el qubit objetivo cuando el qubit de control es 1. Por ejemplo, una entrada de{000}$-ket $ no dará lugar a ningún cambio ya que el primer qubit (el control) es 0. Sin embargo, tome un caso en el que el{100}primer qubit es 1 - por ejemplo, una entrada de $-ket $. En este caso, la salida{110}es $-ket $ como el segundo qubit (el objetivo) es volteado por la puerta CNOT.

Ahora vamos a considerar nuestra salida una vez que la puerta CNOT ha actuado en nuestra entrada anterior. El resultado es el siguiente:

$$ á frac,{2}alpha, sqrt,{000} etc., etc. y áfrac,{2}alpha,{011} etc. y áclomenos, etc.{2}{110} {2}{101}

El siguiente paso para enviar el __mensaje__ es aplicar una puerta de Hadamard al __mensaje__ qubit (ese es el primer qubit de cada término). 

Como recordatorio, la puerta de Hadamard hace lo siguiente:

Entrada | Output
---------------------------| ---------------------------------------------------------------
$-ket{0}$  | $-frac{1}ásqrt{2}('ket+{0} ''ket')'{1}
$-ket{1}$  | $-frac{1}ásqrt{2}(ket{0} - áket{1})$

Si aplicamos la puerta de Hadamard al primer qubit de cada término de nuestra salida anterior, obtenemos el siguiente resultado:

$$ á frac, alpha, sqrt,{2}{1}etc., frac,{2}sqrt, etc. (ket{0} + ket{1})) , ket{00} {2}+ á{1}frac, alpha,{2}(frac,{0} alpha,{1}"frac"{11} y "sqrt" ("frac"{2}("ket" + "ket") (ket ) y "ket" (") frac-beta-sqrt{1}{2}(frac, sqrt, etc.,{1}{01} {0} "ket" y{1}"ket)", "ket", "ket", "ket",{10} "frac" y{2}"beta", "frac",{1}"frac", "sqrt"{2}("ket"{0} y "ket" )", "ket" $$

Tenga en cuenta que cada{1}término tiene{2}dos factores $-frac-sqrt-$. Podemos multiplicarlos dando el siguiente resultado:

$$ á frac-alpha-('''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''{2}{0} {1}{00} {2}{0} {1}{11} {2}{0} {1}{10} {2}{0} {1}{01}

El factor{1}{2}$-frac $ es común a cada término, por lo que ahora podemos llevarlo fuera de los corchetes:

$${1}{2}áfrac ábig[-alpha('ket{0} {1}+ 'ket ''ket'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''{00} {0} {1}{11} {0} {1}{10} {0} {1}{01}

A continuación, podemos multiplicar los corchetes para cada término dando:

{1}{2}$$ áfrac ábig ['alpha'ket{000} +{100} ''alpha'ket +{011} ''alpha''ket + ''alpha'ket{111} + ''beta'ket'{010} ' ''beta'ket{110} + 'beta'ket'{001} '{101}

### <a name="step-3-measure-the-result"></a>Paso 3: Mida el resultado

Debido a __que aquí__ y __allá__ se enredan, cualquier medida en __aquí__ afectará el estado de __allí.__ Si medimos el primer y segundo qubit (__mensaje__ y __aquí__) podemos aprender en qué estado __hay,__ debido a esta propiedad de enredo. 

* Si medimos y obtenemos un resultado 00, la superposición se contrae, dejando solo los términos coherentes con este resultado. Eso es $-alpha-ket{000} +-beta-ket{001}$. Esto se puede refactorizar{00}a $-ket{0} ('alpha'ket+'beta'ket{1}''$' . Por lo tanto, si medimos el primer y segundo qubit para que sea 00, sabemos{0} que el tercer{1}qubit, __allí__, está en el estado $('alpha'ket +'beta'ket )$.
* Si medimos y obtenemos un resultado 01, la superposición se contrae, dejando solo los términos coherentes con este resultado. Eso es $-alpha-ket{011} +-beta-ket{010}$. Esto se puede refactorizar{01}a $-ket{1} ('alpha'ket+'beta'ket{0}''$' . Por lo tanto, si medimos el primer y segundo qubit para que sea 01, sabemos{1} que el tercer{0}qubit, __allí__, está en el estado $('alpha'ket +'beta'ket )$.
* Si medimos y obtenemos un resultado 10, la superposición colapsa, dejando solo términos consistentes con este resultado. Eso es $-alpha-ket{100} --beta-ket{101}$. Esto se puede refactorizar{10}a $-ket{0} ('alpha'ket{1}''beta'ket ''$' . Por lo tanto, si medimos el primer y segundo qubit para que sea 10, sabemos{0} que el tercer{1}qubit, __allí__, está en el estado $('alpha'ket -'beta'ket )$.
* Si medimos y obtenemos un resultado 11, la superposición colapsa, dejando solo términos consistentes con este resultado. Eso es $-alpha-ket{111} --beta-ket{110}$. Esto se puede refactorizar{11}a $-ket{1} ('alpha'ket{0}''beta'ket ''$' . Por lo tanto, si medimos el primer y segundo qubit para que sea 11, sabemos{1} que el tercer{0}qubit, __allí__, está en el estado $('alpha'ket -'beta'ket )$.

### <a name="step-4-interpret-the-result"></a>Paso 4: Interpretar el resultado

Como recordatorio, el __mensaje__ original que deseamos enviar era:

$$ á ket,psi, á alpha, ket{0} +{1} ábeta, $$

Tenemos que poner el __qubit allí__ en este estado, para que el estado recibido sea el que se pretendía. 

* Si medimos y obtuvimos un resultado de 00, entonces el tercer qubit, __allí__, está en el estado $('alpha'ket{0} +'beta'ket{1})$. Como este es el __mensaje__previsto, no se requiere ninguna alteración.
* Si medimos y obtuvimos un resultado de 01, entonces el tercer qubit, __allí__, está en el estado $('alpha'ket{1} +'beta'ket{0})$. Esto difiere del __mensaje__previsto, sin embargo, la aplicación de una{0} puerta NOT nos{1}da el estado deseado $('alpha'ket+'beta'ket )$.
* Si medimos y obtuvimos un resultado de 10, entonces el tercer qubit, __allí__, está en el estado $('alpha'ket{0} -'beta'ket{1})$. Esto difiere del __mensaje__previsto, sin embargo, la aplicación de una{0} puerta Z nos{1}da el estado deseado $('alpha'ket +'beta'ket )$.
* Si medimos y obtuvimos un resultado de 11, entonces el tercer qubit, __allí__, está en el estado $('alpha'ket{1} -'beta'ket{0})$. Esto difiere del __mensaje__previsto, sin embargo, la aplicación de una puerta NOT seguida{0} de una puerta{1}Z nos da el estado deseado $(-alpha-ket +-beta-ket )$.

En resumen, si medimos y el primer qubit es 1, se aplica una puerta Z. Si medimos y el segundo qubit es 1, se aplica una puerta NOT.

### <a name="summary"></a>Resumen
A continuación se muestra un circuito cuántico de libro de texto que implementa la teletransportación. Pasando de izquierda a derecha se puede ver:
- Paso 1: Enredado __aquí__ y __allá__ mediante la aplicación de una puerta Hadamard y puerta CNOT.
- Paso 2: Enviar el __mensaje__ usando una puerta CNOT y una puerta Hadamard.
- Paso 3: Tomando una medida del primer y segundo qubits, __mensaje__ y __aquí__.
- Paso 4: Aplicar una puerta NO o una puerta Z, dependiendo del resultado de la medición en el paso 3.

!['Teleport(msg : Qubit, hay : Qubit) : Unidad'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Teletransportación cuántica: Código

Tenemos nuestro circuito de teletransportación cuántica:

!['Teleport(msg : Qubit, hay : Qubit) : Unidad'](~/media/teleportation.svg)

Ahora podemos traducir cada uno de los pasos de este circuito cuántico en Q.

### <a name="step-0-definition"></a>Paso 0: Definición
Cuando realizamos la teletransportación, debemos conocer el __mensaje__ que deseamos enviar, y dónde queremos enviarlo __(allí).__ Por esta razón, comenzamos definiendo una nueva operación de Teletransporte `msg` `there`a la que se le dan dos qubits como argumentos, y:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

También necesitamos asignar un `here` qubit que `using` logramos con un bloque:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Paso 1: Crear un estado enredado
A continuación, podemos crear el `here` `there` par entre @"microsoft.quantum.intrinsic.h" @"microsoft.quantum.intrinsic.cnot" y mediante las operaciones:

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Paso 2: Enviar el mensaje
A continuación, usamos las siguientes puertas $-nombredeusuario-CNOT-$ y $H$ para mover nuestro mensaje qubit:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Paso 3 & 4: Medición e interpretación del resultado
Por último, @"microsoft.quantum.intrinsic.m" utilizamos para realizar las mediciones y realizar las operaciones `if` de puerta necesarias para obtener el estado deseado, como se indica mediante instrucciones:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a>Paso 5: Reiniciar el registro qubit

Al final de cada operación de Q, tenemos que{0}dejar que los qubits en el estado $-ket $. Podemos usar @"microsoft.quantum.intrinsic.reset" para reiniciar todos los qubits al estado cero y esto terminará nuestra operación.

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


