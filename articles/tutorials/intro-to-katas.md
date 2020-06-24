---
title: Introducción a Quantum Katas
description: Obtenga información sobre los katas (ejercicios de entrenamiento) proporcionados con el kit de desarrollo de Microsoft Quantum (QDK)
author: bradben
ms.author: bradben
ms.date: 06/02/2020
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 1c4dfa5c47aa38935cd5936cd256e357b6605371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276219"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Conozca la computación cuántica con Quantum Katas

[Los katas Quantum](https://github.com/Microsoft/QuantumKatas/) son tutoriales de código abierto, tutoriales autoguiados y ejercicios de programación destinados a la enseñanza de elementos de Quantum Computing y la programación de Q # al mismo tiempo.

## <a name="learning-by-doing"></a>Aprendizaje práctico

Los tutoriales y ejercicios recopilados en este proyecto resaltan el aprendizaje práctico: ofrecen tareas de programación que abarcan determinados temas que progresan desde muy sencillo a muy desafiante. Cada tarea requiere que complete un código; las primeras tareas pueden requerir solo una línea y las últimas pueden requerir un fragmento variable de código.

Lo más importante es que los katas incluyen marcos de pruebas que configuran, ejecutan y validan las soluciones para las tareas. Esto le permite obtener comentarios inmediatos sobre su solución y reconsiderar su enfoque en caso de que fuera incorrecto.

Puede usar katas para aprender en el entorno que prefiera:

* Cuadernos de Jupyter en línea dentro del entorno del enlazador
* Cuadernos de Jupyter que se ejecutan en su máquina local
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>¿Qué se puede aprender con Quantum Katas?

Explore los aspectos básicos y los fundamentos de la informática Quantum o profundice en los algoritmos y protocolos Quantum. Le recomendamos que siga esta ruta de aprendizaje al principio para adquirir una idea sólida de los conceptos fundamentales de la computación cuántica. Por supuesto, puede omitir los temas con los que está familiarizado, como la aritmética compleja, y aprender los algoritmos en el orden que desee.

### <a name="introduction-to-quantum-computing-concepts"></a>Introducción a los conceptos de computación cuántica

| Kata | Descripción |
|:-----|-------------|
|[Aritmética compleja](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)|En este tutorial se explica parte del fondo matemático necesario para trabajar con la informática Quantum, como números imaginarios y complejos.|
|[Álgebra lineal](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)|El álgebra lineal se usa para representar los Estados y las operaciones de Quantum en la informática Quantum. En este tutorial se tratan los conceptos básicos, incluidas matrices y vectores.|
|[Concepto de cúbit](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/Qubit)|Más información sobre qubits: uno de los conceptos principales de la informática Quantum. |
|[Puertas cuánticas de un solo cúbit](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates)|En este tutorial se presentan las puertas de Quantum de un solo qubit, que actúan como los bloques de creación de los algoritmos Quantum y transforman los Estados qubit Quantum de varias maneras.|
|[Sistemas de varios cúbits](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitSystems)|En este tutorial se presentan sistemas de varios qubit, su representación en notación matemática y en código de Q #, y el concepto de inenredo.|
|[Puertas de Quantum multiqubit](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitGates)|Este tutorial sigue el tutorial de las [puertas de Quantum de un solo qubit](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates) y se centra en la aplicación de las puertas de Quantum a sistemas de varios qubit.|

### <a name="quantum-computing-fundamentals"></a>Conceptos básicos de la computación cuántica

| Kata | Descripción |
|:-----|-------------|
|[Reconocimiento de puertas cuánticas](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)|Una serie de ejercicios diseñados para ayudarle a familiarizarse con las puertas de Quantum básicas en Q #. Incluye ejercicios para las puertas básicas de un solo qubit y de varios qubit, el método contiguo y las puertas controladas, y cómo usar las puertas para modificar el estado de una qubit.|
|[Creación de una superposición cuántica](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)|Use estos ejercicios para familiarizarse con el concepto de superposición y programación en Q #. Incluye ejercicios para puertas de qubit único y multiqubit básicas, superposición y control de flujo y recursividad en Q #.|
|[Distinción de los estados cuánticos mediante medidas](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)|Solucione estos ejercicios mientras aprende sobre la medición de Quantum y los Estados ortogonal y no ortogonal. |
|[Medidas combinadas](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)|Obtenga información sobre las medidas de paridad juntas y cómo usar la operación [Measure](xref:microsoft.quantum.intrinsic.measure) para distinguir los Estados de Quantum.|

### <a name="algorithms"></a>Algoritmos

| Kata | Descripción |
|:-----|-------------|
|[Teleportabilidad cuántica](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)|Este Kata explora la teletransportación Quantum: un protocolo que permite la comunicación de un estado de Quantum usando solo la comunicación clásica y el desenredo de Quantum previamente compartida.|
|[Codificación superdensa](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)|La codificación de superdensa es un protocolo que permite la transmisión de dos bits de información clásica mediante el envío de un solo qubit con el inenredo de Quantum previamente compartido.  |
|[Algoritmo de Deutsch-Jozsa](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringDeutschJozsaAlgorithm)|Este algoritmo es famoso para ser uno de los primeros ejemplos de un algoritmo Quantum que es exponencialmente más rápido que cualquier algoritmo clásico determinista.|
|[Exploración de las propiedades generales del algoritmo de búsqueda de Grover](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringGroversAlgorithm)|Una introducción de alto nivel a uno de los algoritmos más famosos de la informática Quantum. Resuelve el problema de buscar una entrada en un cuadro negro (Oracle) que genera una salida determinada. |
|[Implementación del algoritmo de búsqueda de Grover](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)|Esta Kata se profundiza en el algoritmo de búsqueda de Grover y trata la escritura de Oracle, la realización de pasos del algoritmo y, por último, su colocación conjunta.|
|[Solución de problemas reales con el algoritmo de Grover: problemas de SAT](https://github.com/microsoft/QuantumKatas/tree/master/SolveSATWithGrover)|Una serie de ejercicios que usa el algoritmo de Grover para solucionar problemas realistas, mediante el uso de [problemas de satisfiability booleanos](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem) (SAT) como ejemplo.  |
|[Solución de problemas reales con el algoritmo de Grover: problemas de color del gráfico](https://github.com/microsoft/QuantumKatas/tree/master/GraphColoring)| Este Kata explora el algoritmo de Grover, esta vez para solucionar [problemas de satisfacción de restricciones](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem), con un problema de color de gráfico como ejemplo. |

### <a name="protocols-and-libraries"></a>Protocolos y bibliotecas

| Kata | Descripción |
|:-----|-------------|
|[Protocolo BB84 para la distribución cuántica de claves](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)|Aprenda e implemente un protocolo de distribución de claves Quantum, [BB84](https://en.wikipedia.org/wiki/BB84), con qubits para intercambiar claves criptográficas. |
|[Error de volteo del código de corrección de bits](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)|Explore la corrección de errores de Quantum con los códigos de corrección de errores de Quantum (QEC) más sencillos (el código de tres qubit bits-Flip).|
|[Estimación de la fase](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)|Los algoritmos de estimación de fase son algunos de los bloques de creación más fundamentales de la informática Quantum. Obtenga información sobre la estimación de fase con estos ejercicios que cubren la estimación de la fase Quantum y cómo preparar y ejecutar rutinas de estimación de fase en Q #.|
|[Aritmética de Quantum: creación de agregados de rizo](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)|Una serie detallada de ejercicios que exploran la adición de [rizo](https://en.wikipedia.org/wiki/Adder_(electronics)#Ripple-carry_adder) en un equipo Quantum. Cree un agregador de Quantum en contexto, expándalo con un algoritmo diferente y, por último, cree un Subtractor de Quantum en contexto.   |

### <a name="entanglement-games"></a>Juegos de entrelazamiento

| Kata | Descripción |
|:-----|-------------|
|[Juego CHSH](https://github.com/microsoft/QuantumKatas/tree/master/CHSHGame)|Explore la inenredo de Quantum con una implementación del juego [CHSH](https://en.wikipedia.org/wiki/CHSH_inequality) . Este juego no [local](https://en.wikipedia.org/wiki/Quantum_refereed_game) muestra cómo se puede usar el incumplimiento de Quantum para aumentar la posibilidad de que los jugadores puedan ganar más allá de lo que sería posible con una estrategia puramente clásica.|
|[Juego GHZ](https://github.com/microsoft/QuantumKatas/tree/master/GHZGame)|El juego GHZ es otro juego no local, pero implica tres jugadores.|
|[Juego del cuadrado mágico de Mermin-Peres](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)|Una serie de ejercicios que exploran la [seudoclase de Quantum](https://en.wikipedia.org/wiki/Quantum_pseudo-telepathy#The_Mermin%E2%80%93Peres_magic_square_game) para resolver un juego mágico.  |

## <a name="resources"></a>Recursos

Vea la serie completa de [Quantum Katas](https://github.com/microsoft/QuantumKatas)

[Ejecutar los katas online](https://aka.ms/try-quantum-katas)
