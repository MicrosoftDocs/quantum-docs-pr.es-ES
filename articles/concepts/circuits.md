---
title: Circuitos cuánticos
description: Obtenga información sobre cómo representar visualmente operaciones Quantum simples y complejas con diagramas de circuito de Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 59c32928ddc9252009ad101a3cf3ac33f4968e28
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269616"
---
# <a name="quantum-circuits"></a>Circuitos Quantum
Considere, por un momento, la transformación unitario $ \text { CNOT} _ {01 } (H \otimes 1) $.
Esta secuencia de la puerta es de importancia fundamental para la informática de Quantum, ya que crea un estado de dos qubit con el máximo de supuestos:

$ $ \mathrm{CNOT}_{01 } (H \otimes 1) \ket{00 } = \frac{1 } {\sqrt{2 } } \left (\ket{00 } + \ket{11 } \right), $ $

Las operaciones con esta complejidad o mayor son ubicuas en los algoritmos Quantum y la corrección de errores Quantum, por lo que debe ser una buena forma de que hay un método simple para su visualización denominado *Diagrama de circuito Quantum*.
El diagrama del circuito para preparar este estado de Quantum con el máximo grado de enredo es:

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de circuitos para un estado de dos qubits con un máximo de enredo](~/media/1.svg)

## <a name="quantum-circuit-diagram-conventions"></a>Convenciones de diagrama del circuito de Quantum
Este lenguaje visual para las operaciones Quantum puede ser más fácil de entender que escribir su matriz equivalente una vez que comprenda las convenciones para expresar un circuito de Quantum.
Revisaremos estas convenciones a continuación.

En un diagrama de circuitos, cada línea sólida muestra un qubit o, en general, un registro qubit.
Por Convención, la línea superior es qubit Register $0 $ y el resto se etiqueta secuencialmente. El circuito de ejemplo anterior se representa como si actuara en dos qubits (o equivalentes en dos registros que se componen de un qubit).
Las puertas que actúan en uno o varios registros de qubit se indican como un cuadro.
Por ejemplo, el símbolo

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Símbolo para una operación de Hadamard que actúa en un registro de un solo qubit](~/media/2.svg)

es una operación de [Hadamard](xref:microsoft.quantum.intrinsic.h) que actúa en un registro de un solo qubit.

Las puertas de Quantum se ordenan cronológicamente con la puerta situada más a la izquierda como la puerta que se aplica primero a qubits.
En otras palabras, si se imagen de los cables como que contienen el estado de Quantum, los cables llevan el estado de Quantum a través de cada una de las puertas del diagrama de izquierda a derecha.
Es decir 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de las puertas de Quantum aplicadas de izquierda a derecha](~/media/3.svg)

es la matriz de unitario $CBA $ .
La multiplicación de matrices obedece la Convención opuesta: primero se aplica la matriz que se encuentra más a la derecha. Sin embargo, en los diagramas de circuito Quantum, se aplica primero la puerta situada más a la izquierda.
En ocasiones, esta diferencia puede llevar a confusión, por lo que es importante tener en cuenta esta diferencia significativa entre los diagramas de la notación algebraico lineal y del circuito de Quantum.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Entradas y salidas de los circuitos Quantum
Todos los ejemplos anteriores han tenido exactamente el mismo número de entradas de cables (qubits) en una puerta de Quantum como el número de cables de la puerta de Quantum.
En primer lugar, es posible que parezca razonable que los circuitos Quantum pudieran tener más salidas que las entradas en general.
Sin embargo, esto no es posible, ya que todas las operaciones de Quantum, la medida de guardado, son unitarios y, por tanto, reversibles.
Si no tenían el mismo número de salidas que las entradas, no serían reversibles y, por lo tanto, no serían una contradicción.
Por esta razón, todos los cuadros dibujados en un diagrama de circuitos deben tener exactamente el mismo número de cables que lo señalan.

Los diagramas de circuitos de varios qubit siguen convenciones similares a las de qubit.
Como ejemplo de clarificación, podemos definir una operación de $B unitario de dos qubit $ para que sea $ (H S \otimes X) $ y expresar el circuito de forma equivalente.

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de circuitos de una operación de unitario de dos qubit](~/media/4.svg)

También podemos ver $B $ como si tuviera una acción en un solo registro de dos qubit, en lugar de en 2 1-qubit, en función del contexto en el que se use el circuito. Quizás la propiedad más útil de estos diagramas de circuitos abstractos es que permiten describir algoritmos Quantum complicados en un nivel alto sin tener que compilarlos en las puertas fundamentales.
Esto significa que puede obtener un Intuition sobre el flujo de datos para un algoritmo Quantum grande sin necesidad de comprender todos los detalles de cómo funciona cada una de las subrutinas dentro del algoritmo.

## <a name="controlled-gates"></a>Puertas controladas
La otra construcción que se integra en los diagramas del circuito de Quantum de varios qubit es control.
La acción de una puerta de Quantum controlada por una vez, indicada como $ \Lambda (G) $, donde un valor de qubit único controla la aplicación de $G $ , se puede entender examinando el siguiente ejemplo de una entrada de estado de producto $ \Lambda (G) (\alpha \ket{0 } + \beta \ket{1 } ) \ket { \psi } = \alpha \ket{0 } \ket { \psi } + \beta \ket{1 } G \ket { \psi } $.
Es decir, la barrera controlada se aplica $G $ al registro que contiene $ \psi $ si y solo si el control qubit toma el valor $1 $ .
En general, se describen las operaciones controladas en diagramas de circuitos como

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de circuitos de una puerta controlada por una sola vez](~/media/5.svg)

Aquí el círculo negro denota el bit de Quantum en el que se controla la puerta y una conexión vertical denota la unitario que se aplica cuando el control qubit toma el valor $1 $ .
Para los casos especiales en los que $G = X $ y $G = Z $ , presentamos la siguiente notación para describir la versión controlada de las puertas (tenga en cuenta que la puerta controlada-X es la [ $ puerta $CNOT](xref:microsoft.quantum.intrinsic.cnot)):

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de circuitos para casos especiales de puertas controladas](~/media/6.svg)

Q # proporciona métodos para generar automáticamente la versión controlada de una operación, lo que evita que el programador tenga que codificar estas operaciones. A continuación se muestra un ejemplo de esto:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Operador de medida
La operación restante para visualizar en diagramas de circuitos es la medida.
La medición toma un registro de qubit, lo mide y genera el resultado como información clásica.
Una operación de medición se denota mediante un símbolo de medidor y siempre toma como entrada un registro qubit (indicado por una línea sólida) y genera información clásica (se indica mediante una línea doble).
En concreto, este Subcircuito tiene el siguiente aspecto:

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Símbolo que representa una operación de medición](~/media/7.svg)

Q # implementa un [operador de medida](xref:microsoft.quantum.intrinsic.measure) para este fin.
Vea la [sección sobre medidas](xref:microsoft.quantum.libraries.standard.prelude#measurements) para obtener más información.

Del mismo modo, el Subcircuito

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de circuito que representa una operación controlada](~/media/8.svg)

proporciona una puerta controlada por clases, donde $G $ se aplica en el bit de control clásico que es el valor $1 $ .

## <a name="teleportation-circuit-diagram"></a>Diagrama del circuito de teleportabilidad
La teleportabilidad de Quantum es quizás el mejor algoritmo Quantum para ilustrar estos componentes.
Puede obtener información sobre el uso de la teleportabilidad Quantum de Quantum [Kata](xref:microsoft.quantum.overview.katas) Quantum para mover datos dentro de un equipo Quantum (o incluso entre equipos Quantum distantes en una red Quantum) mediante el uso de la inenredo y la medición.
Curiosamente, realmente es capaz de mover un estado de Quantum, por ejemplo, el valor de un qubit determinado, de un qubit a otro, sin tener que saber aún cuál es el valor de qubit.
Esto es necesario para que el protocolo funcione según las leyes de la mecánica de Quantum.
A continuación se proporciona el circuito de teleportabilidad de Quantum; También proporcionamos una versión anotada del circuito para ilustrar cómo leer el circuito de Quantum.

<!--- ![](.\media\tp2.svg){ width=50% } --->
![Circuito de teleportabilidad de Quantum](~/media/tp2.svg)
