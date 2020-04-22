---
title: Glosario de computación cuántica
description: Un glosario de términos comunes, acciones y objetos utilizados en la computación cuántica.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ee78515a0f47730b7d3df10da0853c5b8a7f6624
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81482219"
---
# <a name="quantum-computing-glossary"></a>Glosario de computación cuántica

## <a name="adjoint"></a>Adjunto

La compleja transposición conjugada de una [operación](xref:microsoft.quantum.glossary#operation). Para las operaciones que implementan un operador [unitario,](xref:microsoft.quantum.glossary#unitary-operator) la junta es la inversa de la operación y se indica mediante un símbolo de daga. Por ejemplo, si `U` la operación representa el `Adjoint U` operador unitario $U$, a continuación, representa $U -dagger$. Para obtener más información, consulte [Adjoint](xref:microsoft.quantum.language.file-structure#adjoint).

## <a name="ancilla"></a>Ancilla

Un [qubit](xref:microsoft.quantum.glossary#qubit) que sirve como memoria temporal para una computadora cuántica y se asigna y desasigna según sea necesario.  Para obtener más información, consulte [Múltiples qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Estado de Bell

Uno de los cuatro [estados cuánticos](xref:microsoft.quantum.glossary#quantum-state) [enredados](xref:microsoft.quantum.glossary#entanglement) al máximo específicos de dos qubits. Los cuatro estados se definen $-ket-beta_-ij----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------{00} {11}{2} Un estado Bell también se conoce como [un par EPR.](xref:microsoft.quantum.glossary#epr-pair)

## <a name="bloch-sphere"></a>Esfera Bloch

Representación gráfica de un [estado cuántico](xref:microsoft.quantum.glossary#quantum-state) de un solo[qubit](xref:microsoft.quantum.glossary#qubit) como punto en una esfera de unidad tridimensional. Para obtener más información, consulte Visualización de [Qubits y transformaciones mediante Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Accesible

Una [operación](xref:microsoft.quantum.glossary#operation) o [función](xref:microsoft.quantum.glossary#function) en el lenguaje Q. Para obtener más información, consulte [Tipos de operación y función](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="clifford-group"></a>Grupo Clifford

El conjunto de operaciones que ocupan los octetos de la [esfera Bloch](xref:microsoft.quantum.glossary#bloch-sphere) y las permutaciones de efecto de los [operadores Pauli.](xref:microsoft.quantum.glossary#pauli-operators) Estas incluyen las operaciones [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$](xref:microsoft.quantum.intrinsic.y), [$Z$](xref:microsoft.quantum.intrinsic.z), [$H$](xref:microsoft.quantum.intrinsic.h) y [$S$](xref:microsoft.quantum.intrinsic.s).

## <a name="controlled"></a>Controlado

Una [operación](xref:microsoft.quantum.glossary#operation) cuántica que toma uno o más [qubits](xref:microsoft.quantum.glossary#qubit) como activadores para la operación de destino. Para obtener más información, consulte [Controlado](xref:microsoft.quantum.language.type-model#controlled).

## <a name="dirac-notation"></a>Notación Dirac

Una abreviatura simbólica que simplifica la representación de [estados cuánticos,](xref:microsoft.quantum.glossary#quantum-state)también llamado notación *bra-ket.*  La porción de *sujetador* representa un vector de fila, por ejemplo $-bra-A--------&------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- *ket* \\ \\ Para obtener más información, consulte [Notación dirac](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Valor propio

El factor por el cual la magnitud de un [eigenvector](xref:microsoft.quantum.glossary#eigenvector) de una transformación dada cambia por la aplicación de la transformación.  Dada una matriz cuadrada $M$ y un eigenvector $v$, entonces $Mv cv$, donde $c$ es el valor propio y puede ser un número complejo de cualquier argumento. Para obtener más información, consulte [Conceptos](xref:microsoft.quantum.concepts.matrix-advanced)de matriz avanzada .

## <a name="eigenvector"></a>Eigenvector

Un vector cuya dirección no cambia por una transformación determinada y cuya magnitud cambia por un factor correspondiente al [valor propio](xref:microsoft.quantum.glossary#eigenvalue)de ese vector. Dada una matriz cuadrada $M$ y un valor propio $c$, a continuación, $Mv cv$, donde $v$ es un eigenvector de la matriz y puede ser un número complejo de cualquier argumento. Para obtener más información, consulte [Conceptos](xref:microsoft.quantum.concepts.matrix-advanced)de matriz avanzada .

## <a name="entanglement"></a>Enredo

Las partículas cuánticas, como [los qubits,](xref:microsoft.quantum.glossary#qubit)se pueden conectar o *enredar* de forma que no se puedan describir independientemente unas de otras. Sus resultados de medición se correlacionan incluso cuando están separados infinitamente lejos. El enredo es esencial para [medir](xref:microsoft.quantum.glossary#measurement) el [estado](xref:microsoft.quantum.glossary#quantum-state) de un qubit.  Para obtener más información, consulte [Conceptos](xref:microsoft.quantum.concepts.matrix-advanced)de matriz avanzada .

## <a name="epr-pair"></a>Par EPR

Uno de los cuatro estados [cuánticos](xref:microsoft.quantum.glossary#quantum-state) específicos enredados al máximo de dos [qubits.](xref:microsoft.quantum.glossary#qubit) Los cuatro estados se definen $-ket-beta_-ij-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------{1} {00} {11}{2} Un par de EPR también se conoce como [estado Bell](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Evolución

Cómo cambia un [estado cuántico](xref:microsoft.quantum.glossary#quantum-state) con el tiempo. Para obtener más información, consulte [Matriz exponencial .](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)

## <a name="function"></a>Función
Un tipo de subrutina en el lenguaje Q- que es puramente clásica (no cuántica). Mientras que las funciones se utilizan dentro de algoritmos cuánticos, no pueden actuar sobre [qubits](xref:microsoft.quantum.glossary#qubit) o [operaciones](xref:microsoft.quantum.glossary#operation)de llamada. Para obtener más información, consulte [Tipos de operación y función](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="gate"></a>Puerta

Un término heredado para una [operación](xref:microsoft.quantum.glossary#operation)cuántica, basado en el concepto de puertas lógicas clásicas. Un [circuito cuántico](xref:microsoft.quantum.glossary#quantum-circuit-diagram) es una red de puertas (u operaciones), basada en el concepto similar de circuitos lógicos clásicos.

## <a name="global-phase"></a>Fase global

Cuando dos [estados](xref:microsoft.quantum.glossary#quantum-state) son idénticos a un múltiplo de un número complejo $e,i,phi$, se dice que difieren hasta una fase global. A diferencia de las fases locales, las fases globales no pueden observarse a través de ninguna [medición.](xref:microsoft.quantum.glossary#measurement) Para obtener más información, consulte [El Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

La operación Hadamard (también conocida como la puerta o transformación de Hadamard) actúa en un{0}solo [qubit](xref:microsoft.quantum.glossary#qubit) y lo coloca en una [superposición](xref:microsoft.quantum.glossary#superposition) uniforme de $-ket $ o $-ket{1}$ si el qubit está inicialmente en el estado $-ket{0}$. La operación predefinida [`H`](xref:microsoft.quantum.intrinsic.h) aplica esta operación en Q.

## <a name="immutable"></a>Inmutable

Variable cuyo valor no se puede cambiar. Se crea una variable inmutable `let` en Q- mediante la palabra clave. Para declarar variables que se *pueden* cambiar, utilice `set` la palabra clave [mutable](xref:microsoft.quantum.glossary#immutable) para declarar y la palabra clave para modificar el valor. 

## <a name="measurement"></a>Medición

Una manipulación de un [qubit](xref:microsoft.quantum.glossary#qubit) (o conjunto de qubits) que produce el resultado de una observación, obteniendo en efecto un bit clásico. Para obtener más información, consulte [El Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Mutable

Variable cuyo valor se puede cambiar después de crearla. Se declara una variable mutable `mutable` en Q- `set` mediante la palabra clave y se modifica mediante la palabra clave. Las variables `let` creadas con la palabra clave son [inmutables](xref:microsoft.quantum.glossary#immutable) y su valor no se puede cambiar.

## <a name="namespace"></a>Espacio de nombres

Una etiqueta para una colección de nombres relacionados (es decir, [operaciones,](xref:microsoft.quantum.glossary#operation) [funciones](xref:microsoft.quantum.glossary#function)y [tipos definidos por](xref:microsoft.quantum.glossary#user-defined-type)el usuario). Por ejemplo, el espacio de nombres [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) etiqueta todos los símbolos definidos en la biblioteca estándar que ayudan a preparar los estados iniciales.

## <a name="operation"></a>Operación

La unidad básica de ejecución cuántica en Q. Es aproximadamente equivalente a una función en C, C+ o Python, o un método estático en C o Java. Para obtener más información, consulte [Tipos de operación y función](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="operator-application"></a>Aplicación del operador

Realizar una operación cuántica. Esto normalmente aplica una matriz unitaria al vector de estado cuántico actual.

## <a name="oracle"></a>Oracle

Una subrutina que proporciona información dependiente de datos a un algoritmo cuántico en tiempo de ejecución. Normalmente, el objetivo es proporcionar una [superposición](xref:microsoft.quantum.glossary#superposition) de salidas correspondientes a las entradas que están en superposición. Para obtener más información, consulte [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Aplicación parcial

Llamar a una [función](xref:microsoft.quantum.glossary#function) u [operación](xref:microsoft.quantum.glossary#operation) sin todas las entradas necesarias. Esto devuelve un nuevo [invocable](xref:microsoft.quantum.glossary#callable) que solo necesita los parámetros que faltan (indicados por un carácter de subrayado) que se deben proporcionar durante una aplicación futura. Por ejemplo, dada `MyFunc(x : int, y : int) : int {return x + y;}` la función se puede `let NewFunc = MyFunc(_, 3)`aplicar parcialmente a una nueva función. A continuación, puede llamar a la nueva `NewFunc(2)` función en un momento posterior con el parámetro que falta, que devuelve el valor *5*.  Para obtener más información, consulte [Aplicación parcial](xref:microsoft.quantum.language.expressions#partial-application).

## <a name="pauli-operators"></a>Operadores Pauli

Un conjunto de tres matrices unitarias `X`de `Y` `Z` 2 x 2 conocidas como las operaciones , y cuánticas. La matriz de identidad, $I$, a menudo también se incluye en el conjunto.  $I \\ \\ & \\ \\ & $X & & de la página de la de la matriz de inicios, $Y, $Y, & -i \\ \\ & 0, $Z, $Z, "begin", "bmatrix" de 1 & 0 \\ \\ 0 & -1 , "fin" y "bmatrix".".   Para obtener más información, consulte [Operaciones de un solo qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagrama de circuito cuántico

Un método para representar gráficamente la secuencia de [operaciones](xref:microsoft.quantum.glossary#operation) (o [puertas)](xref:microsoft.quantum.glossary#gate)para programas cuánticos simples, por ejemplo ![Diagrama](~/media/qpe.png)de circuito de muestra . Para obtener más información, consulte [Circuitos cuánticos](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Bibliotecas cuánticas

Colecciones de [operaciones,](xref:microsoft.quantum.glossary#operation) [funciones](xref:microsoft.quantum.glossary#function) y [tipos definidos por](xref:microsoft.quantum.glossary#user-defined-type) el usuario para la creación de programas Q. La [biblioteca estándar](xref:microsoft.quantum.libraries.standard.intro) está instalada de forma predeterminada. Otras bibliotecas disponibles son la [biblioteca de química,](xref:microsoft.quantum.chemistry.concepts.intro)la [biblioteca numérica](xref:microsoft.quantum.numerics.intro) y la biblioteca de [aprendizaje](xref:microsoft.quantum.machine-learning.concepts.intro)automático.

## <a name="quantum-state"></a>Estado cuántico

El estado preciso de un sistema cuántico aislado, del que se pueden extraer las probabilidades de [medición.](xref:microsoft.quantum.glossary#measurement) En la computación cuántica, el simulador cuántico utiliza esta información para simular cómo los qubits responden a las operaciones. Para obtener más información, consulte [El Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

Una unidad básica de información cuántica, análoga a un *poco* en la informática clásica. Para obtener más información, consulte [El Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Repetición hasta el éxito

Un algoritmo cuántico que probabísticamente tiene éxito. Si se falla, la rutina volverá a intentarlo hasta que se realice correctamente (o se haya alcanzado un límite). Para obtener más información, consulte [Repetir hasta que se haya realizado correctamente (RUS)](xref:microsoft.quantum.techniques.qubits#measurements)

## <a name="standard-libraries"></a>Bibliotecas estándar

[Operaciones,](xref:microsoft.quantum.glossary#operation) [funciones](xref:microsoft.quantum.glossary#function) y [tipos definidos por](xref:microsoft.quantum.glossary#user-defined-type) el usuario que se instalan junto con el compilador Q- durante la instalación. La implementación de la biblioteca estándar es independiente con respecto a las máquinas de destino. Para obtener más información, consulte [Bibliotecas estándar](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Superposición

El concepto en la computación cuántica de que un [qubit](xref:microsoft.quantum.glossary#qubit) es una combinación lineal de dos estados, $-ket-0-$ y $-ket-1-$, hasta que se [mide.](xref:microsoft.quantum.glossary#measurement)  Para obtener más información, consulte Qué es la [computación cuántica](xref:microsoft.quantum.overview.what).

## <a name="target-machine"></a>Máquina de destino

Un destino de compilación que reduce un programa cuántico abstracto hacia el hardware o la simulación. Esto normalmente incluye reescrituras para muchos propósitos, incluyendo reemplazo de puerta, codificación para corrección de errores, diseño geométrico y otros. Para obtener más información, consulte [Simuladores de Quantum y aplicaciones host.](xref:microsoft.quantum.machines)

## <a name="teleportation"></a>Teleportabilidad

Un método para regenerar datos, o el [estado cuántico,](xref:microsoft.quantum.glossary#quantum-state)de un [qubit](xref:microsoft.quantum.glossary#qubit) de un lugar a otro sin mover físicamente el qubit, utilizando [enredo](xref:microsoft.quantum.glossary#entanglement) y [medición.](xref:microsoft.quantum.glossary#measurement)  Para obtener más información, consulte [Circuitos cuánticos](xref:microsoft.quantum.concepts.circuits) y [Colocarlo todo junto.](xref:microsoft.quantum.techniques.puttingittogether)

## <a name="tuple"></a>Tuple

Colección de valores separados por comas que actúa como un único valor. El *tipo* de una tupla se define mediante los tipos de valores que contiene. En Q, las tuplas son [inmutables](xref:microsoft.quantum.glossary#immutable) y se pueden anidar, contener matrices o utilizarse en una matriz. Para obtener más información, consulte [Tipos de tupla](xref:microsoft.quantum.language.type-model#tuple-types).

## <a name="unitary-operator"></a>Operador unitario

Un operador cuyo inverso es igual a su [adjoint](xref:microsoft.quantum.glossary#adjoint), es decir, $UU , daga, á id$.

## <a name="user-defined-type"></a>Tipo definido por el usuario

Colección de tipos integrados o definidos previamente que se pueden denominar una sola unidad. Para obtener más información, consulte [Tipos definidos por](xref:microsoft.quantum.language.type-model#user-defined-types)el usuario .