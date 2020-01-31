---
title: 'Reunir todo: técnicas de Q # | Microsoft Docs'
description: 'Reunir todo: técnicas de preguntas y respuestas'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3605826da159757d4b321dbf4ec6acd7f4e6be05
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820171"
---
# <a name="putting-it-all-together-teleportation"></a>Reunir todo: teleportabilidad #
Volvamos al ejemplo del circuito de teleportabilidad definido en los circuitos de [Quantum](xref:microsoft.quantum.concepts.circuits). Vamos a usar esto para ilustrar los conceptos que hemos aprendido hasta ahora. A continuación se proporciona una explicación de la teleportabilidad de Quantum para quienes no están familiarizados con la teoría, seguidos de un tutorial de la implementación del código en Q #. 

## <a name="quantum-teleportation-theory"></a>Teleportabilidad de Quantum: teoría
La teleportabilidad de Quantum es una técnica para enviar un estado de Quantum desconocido (al que haremos referencia como el "__mensaje__") desde una qubit en una ubicación a una qubit en otra ubicación (nos referiremos a estas qubits como "__aquí__" y "__allí__", respectivamente). Podemos representar el __mensaje__ como un vector mediante la notación Dirac: 

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

Se desconoce el estado del qubit de __mensajes__ , ya que no se conocen los valores de $ \alpha $ y $ \beta $.

### <a name="step-1-create-an-entangled-state"></a>Paso 1: creación de un estado desenredado
Con el fin de enviar el __mensaje__ que necesitamos para que __el qubit se__ qubit __allí__. Esto se logra aplicando una puerta Hadamard, seguida de una puerta CNOT. Echemos un vistazo a las matemáticas detrás de estas operaciones de la puerta.

Comenzaremos con qubits __aquí__ __y en__ el estado $ \ket{0}$. Después de la inenredo de estos qubits, se encuentran en el estado:

$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $

### <a name="step-2-send-the-message"></a>Paso 2: enviar el mensaje
Para enviar el __mensaje__ , primero se aplica una puerta CNOT con el __mensaje__ qubit y __aquí__ qubit como entradas (el __mensaje__ qubit es el control y __aquí__ qubit es el qubit de destino, en esta instancia). Este estado de entrada se puede escribir:

$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $

Se expande a:

$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $

Como recordatorio, la puerta CNOT voltea el qubit de destino cuando el qubit de control es 1. Por ejemplo, una entrada de $ \ket{000}$ no producirá ningún cambio, ya que el primer qubit (el control) es 0. Sin embargo, tome un caso en el que el primer qubit es 1, por ejemplo, una entrada de $ \ket{100}$. En esta instancia, la salida es $ \ket{110}$ como el segundo qubit (el destino) se voltea mediante la puerta CNOT.

Ahora vamos a tener en cuenta la salida una vez que la puerta CNOT haya actuado en la entrada anterior. El resultado es el siguiente:

$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $

El siguiente paso para enviar el __mensaje__ consiste en aplicar una puerta Hadamard al __mensaje__ qubit (que es el primer qubit de cada término). 

Como recordatorio, la puerta Hadamard hace lo siguiente:

Entrada | Output
---------------------------| ---------------------------------------------------------------
$ \ket{0}$  | $ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $
$ \ket{1}$  | $ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $

Si se aplica la puerta Hadamard al primer qubit de cada término de la salida anterior, obtenemos el siguiente resultado:

$ $ \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $

Tenga en cuenta que cada término tiene $2 \frac{1}{\sqrt{2}} $ factores. Podemos multiplicarlos por el siguiente resultado:

$ $ \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $

$ \Frac{1}{2}$ factor es común a cada término, por lo que ahora podemos desecharlo fuera de los corchetes:

$ $ \frac{1}{2}\big [\alpha (\ket{0} + \ket{1}) \ket{00} + \alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $

A continuación, podemos multiplicar los corchetes por cada término:

$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $

### <a name="step-3-measure-the-result"></a>Paso 3: medir el resultado

Debido a __la existencia de__ __aquí__ y, cualquier medida que se produzca __aquí__ afectará al estado de __allí__. Si medimos el primer y el segundo qubit (__mensaje__ y __aquí__) podemos obtener información sobre __el estado en__ el que se encuentra, debido a la propiedad de la inenredo. 

* Si medimos y obtenemos el resultado 00, la superposición se contrae, lo que solo mantiene los términos coherentes con este resultado. Eso es $ \alpha\ket{000} + \beta\ket{001}$. Esto se puede refactorizar a $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $. Por lo tanto, si medimos el primer y el segundo qubit para que sea 00, sabemos que el tercer qubit, __ahí__, está en el estado $ (\alpha\ket{0} + \beta\ket{1}) $.
* Si medimos y obtenemos el resultado 01, la superposición se contrae, lo que solo mantiene los términos coherentes con este resultado. Eso es $ \alpha\ket{011} + \beta\ket{010}$. Esto se puede refactorizar a $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $. Por lo tanto, si medimos el primer y el segundo qubit para que sea 01, sabemos que el tercer qubit, __ahí__, está en el estado $ (\alpha\ket{1} + \beta\ket{0}) $.
* Si medimos y obtenemos el resultado 10, la superposición se contrae, lo que solo mantiene los términos coherentes con este resultado. Ese es $ \alpha\ket{100}-{101}\beta\ket $. Esto se puede refactorizar a $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $. Por lo tanto, si medimos el primer y el segundo qubit para que sea 10, sabemos que el tercer qubit, __ahí__, está en el estado $ (\alpha\ket{0}-\beta\ket{1}) $.
* Si medimos y obtenemos el resultado 11, la superposición se contrae, lo que solo mantiene los términos coherentes con este resultado. Ese es $ \alpha\ket{111}-{110}\beta\ket $. Esto se puede refactorizar a $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $. Por lo tanto, si medimos el primer y el segundo qubit para que sea 11, sabemos que el tercer qubit, __ahí__, está en el estado $ (\alpha\ket{1}-\beta\ket{0}) $.

### <a name="step-4-interpret-the-result"></a>Paso 4: interpretar el resultado

Como recordatorio, el __mensaje__ original que quería enviar era:

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

Necesitamos obtener la qubit en este estado, de modo __que el estado__ recibido sea el que se pretendía. 

* Si medimos y obtuvieron el resultado __00, el tercer qubit, en__el estado $ (\alpha\ket{0} + \beta\ket{1}) $. Como este es el __mensaje__previsto, no se requiere ninguna modificación.
* Si medimos y obtuvieron el resultado __01, el tercer qubit, en__el estado $ (\alpha\ket{1} + \beta\ket{0}) $. Esto difiere del __mensaje__previsto; sin embargo, si se aplica una puerta not, nos proporciona el estado deseado $ (\alpha\ket{0} + \beta\ket{1}) $.
* Si medimos y obtuvieron un resultado de __10, el tercer qubit, en__el estado $ (\alpha\ket{0}-\beta\ket{1}) $. Esto difiere del __mensaje__previsto; sin embargo, la aplicación de una puerta Z nos proporciona el estado deseado $ (\alpha\ket{0} + \beta\ket{1}) $.
* Si medimos y obtuvieron un resultado de __11, el tercer qubit, en__el estado $ (\alpha\ket{1}-\beta\ket{0}) $. Esto difiere del __mensaje__previsto, pero la aplicación de una puerta not seguida de una puerta Z nos proporciona el estado deseado $ (\alpha\ket{0} + \beta\ket{1}) $.

En Resumen, si medimos y el primer qubit es 1, se aplica una puerta Z. Si medimos y el segundo qubit es 1, se aplica una puerta NOT.

### <a name="summary"></a>Resumen
A continuación se muestra un circuito de Quantum de libro de texto que implementa la teleportabilidad. Si se mueve de izquierda a derecha, puede ver:
- Paso 1: desenredo __aquí__ y __allí__ aplicando una puerta HADAMARD y una puerta CNOT.
- Paso 2: enviar el __mensaje__ mediante una puerta CNOT y una puerta Hadamard.
- Paso 3: realizar una medición del primer y segundo qubits, __mensaje__ y __aquí__.
- Paso 4: aplicar una puerta NOT o una puerta Z, dependiendo del resultado de la medición en el paso 3.

![' Teletranspórtate (MSG: qubit, ahí: qubit): unidad '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Teleportabilidad de Quantum: código

Tenemos nuestro circuito para la teleportabilidad de Quantum:

![' Teletranspórtate (MSG: qubit, ahí: qubit): unidad '](~/media/teleportation.svg)

Ahora podemos traducir cada uno de los pasos de este circuito de Quantum en Q #.

### <a name="step-0-definition"></a>Paso 0: definición
Cuando se realiza la teleportabilidad, es necesario conocer el __mensaje__ que se desea enviar y dónde se desea enviarlo (__allí__). Por esta razón, empezamos definiendo una nueva operación de teletransporta con dos qubits como argumentos, `msg` y `there`:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

También necesitamos asignar una `here` qubit que se logra con un bloque de `using`:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Paso 1: creación de un estado desenredado
A continuación, podemos crear el par enenredado entre `here` y `there` mediante las operaciones @"microsoft.quantum.intrinsic.h" y @"microsoft.quantum.intrinsic.cnot":

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Paso 2: enviar el mensaje
Después usamos las siguientes $ \operatorname{CNOT} $ y $H $ Gates para pasar el mensaje qubit:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Paso 3 & 4: medir e interpretar el resultado
Por último, usamos @"microsoft.quantum.intrinsic.m" para realizar las medidas y realizar las operaciones de puerta necesarias para obtener el estado deseado, como se indica en las instrucciones de `if`:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

Esto finaliza la definición de nuestro operador de teleportabilidad, de modo que podemos desasignar `here`, finalizar el cuerpo y finalizar la operación.

```qsharp
    }
}
```
