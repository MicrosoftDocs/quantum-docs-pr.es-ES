---
title: ¿Qué es la computación cuántica?
description: Obtenga información sobre la computación cuántica y lo que puede hacer un equipo cuántico.
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.what
ms.openlocfilehash: 2f3b64b00a0a9552e52e34cb1e3652810b266eab
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529926"
---
# <a name="what-is-quantum-computing"></a>¿Qué es la computación cuántica?

Hay algunos problemas tan difíciles y tan grandes, que aunque todos los superequipos del mundo trabajasen en el problema, se seguiría tardando más tiempo que la vida del universo.

Los equipos cuánticos brindan la posibilidad de resolver algunos de los mayores desafíos del planeta: a nivel ambiental, de la agricultura, la salud, la energía, el clima, la ciencia de los materiales y problemas que aún no se han imaginado. El impacto de los equipos cuánticos tendrá un gran alcance y un gran efecto, como la creación del transistor en 1947, que preparó el camino de la economía digital actual.

La computación cuántica aprovecha el comportamiento exclusivo de la física cuántica para proporcionar un modelo de computación nuevo y potente. La teoría de la física cuántica plantea esa cuestión, a un nivel cuántico puede estar en una superposición de varios estados clásicos. Y esos diferentes estados interfieren entre sí, como las olas en una piscina de olas.  El estado de la materia después de una medida "cae" en uno de los estados clásicos. 

Después, la repetición de la misma medida producirá el mismo resultado clásico.  El entrelazamiento cuántico se produce cuando las partículas interactúan de forma que el estado cuántico de cada una no se puede describir de forma independiente de las demás, aunque las partículas estén físicamente alejadas.  

La computación cuántica almacena información en estados cuánticos de la materia y utiliza su naturaleza cuántica de superposición y entrelazamiento para realizar operaciones cuánticas que procesan esa información, con lo que se aprovechan las interferencias cuánticas y se aprende a programarlas.

La computación cuántica podría parecer intimidante, pero con los recursos adecuados puede empezar a crear aplicaciones cuánticas hoy mismo.

## <a name="the-qubit"></a>El qubit

La computación cuántica define conceptos de computación que reflejan el comportamiento cuántico.  La computación cuántica comienza con la noción de qubit.  En la computación cuántica, un bit cuántico (**qubit**) es una unidad de información cuántica, como un bit clásico. Mientras que los bits clásicos contienen un único valor binario, como 0 o 1, el estado de un qubit puede ser una **superposición** simultánea de 0 y 1.  

La acción de medir un qubit cambia el estado del qubit. Al medir, el qubit pasa de estar en superposición a uno de los estados clásicos.  

También se pueden entrelazar **varios qubits**. Cuando se toma una medida de un qubit entrelazado, se actualizan también los conocimientos del estado de los otros.

## <a name="quantum-algorithms"></a>Algoritmos cuánticos

Los algoritmos cuánticos están diseñados para aprovechar la naturaleza y el comportamiento cuánticos para acelerar los algoritmos clásicos, o para proporcionar formas completamente nuevas de modelado de sistemas físicos.  Estos algoritmos aprovechan la manera en que los qubits codifican la información y la naturaleza paralela de las operaciones en varios qubits entrelazados en superposición.  

Los equipos clásicos codifican la información en bits; cada bit codifica dos valores posibles, 0 o 1.  Un qubit codifica dos valores simultáneamente, 0 y 1.  Dos bits clásicos codifican uno de 4 valores posibles, (00, 01, 10, 11), mientras que dos qubits codifican cualquier superposición de los 4 estados simultáneamente, aunque solo podemos obtener uno de esos valores al medir. Cuatro qubits codifican cualquier superposición de 16 valores simultáneamente, y así sucesivamente, de forma exponencial.  100 qubits pueden codificar más información de la que hay disponible en los sistemas informáticos más grandes actuales.  

Además, cuando varios qubits entrelazados actúan coherentemente, pueden procesar varias opciones simultáneamente. Los qubits entrelazados pueden procesar información en una fracción del tiempo que tardarían incluso los sistemas no cuánticos más rápidos.

El aprovechamiento de estos atributos cuánticos ha sido el objetivo de varias décadas de investigación de algoritmos cuánticos, y se han encontrado muchas técnicas innovadoras que solucionan los problemas en una fracción del tiempo que tardan en resolverse de la forma clásica.  

Uno de los algoritmos cuánticos más famosos es el _algoritmo de Shor_ para la factorización, que hace que el problema tradicionalmente irresoluble de la factorización de un gran número en dos números primos sea lo suficientemente rápida como para desafiar la criptografía tradicional.

En el lado más constructivo, los algoritmos para la distribución segura de claves criptográficas son posibles mediante la superposición, el entrelazamiento cuántico y la propiedad de **no clonación** de los qubits, lo que significa que no se pueden copiar qubits sin detección.

El _algoritmo de Grover_ resalta una técnica de algoritmo cuántico que aumenta a la cuarta potencia la velocidad de búsqueda de datos no estructurados.

## <a name="quantum-hardware"></a>Hardware cuántico

En los equipos clásicos, los bits se corresponden con los niveles de voltaje en los circuitos de silicona. El hardware de computación cuántica se puede implementar mediante diferentes materializaciones físicas de qubits: iones atrapados, superconductores, átomos neutros, espines de electrones, polarización ligera o qubits topológicos. El hardware cuántico es una tecnología emergente. Los qubits son frágiles por naturaleza y son menos coherentes cuando interactúan con su entorno. Es necesario equilibrar la fidelidad del sistema y la escalabilidad. Cuanto mayor sea la escala (es decir, el número de qubits), mayor será la tasa de errores.

Microsoft está desarrollando un equipo cuántico basado en qubits topológicos. Creemos que un qubit topológico se verá menos afectado por los cambios en su entorno, por lo que se reduce el grado de corrección de errores externos. La característica de qubits topológicos aumentó la estabilidad y la resistencia al ruido ambiental, lo que significa que se pueden escalar más fácilmente y seguir siendo confiables durante más tiempo.

## <a name="quantum-computing--a-full-hardware-and-software-stack"></a>Computación cuántica: una pila de software y hardware completa

El programa cuántico de Microsoft es único porque nos centramos en escalar cada uno de los componentes del sistema para ofrecer un impacto cuántico real. Este enfoque completo implica:

* Crear un equipo cuántico mediante qubits topológicos confiables, escalables y tolerantes a los errores. 
* Diseñar un plano de control criogénico único con disipación térmica y bajo consumo. 
* Desarrollar una pila de software completa para habilitar la programación del equipo cuántico y el control del sistema a escala.

Quantum Development Kit (QDK) es un kit de desarrollo de código abierto introducido para que la programación cuántica y el desarrollo de algoritmos sean más accesibles. Nuestro lenguaje de programación de alto nivel, Q#, aborda los desafíos de la programación cuántica.  Hemos diseñado Q# como un lenguaje de programación cuántico de alto nivel centrado en el desarrollo de algoritmos y aplicaciones. El compilador de Q# se integra en una pila de software que permite compilar un algoritmo cuántico en las operaciones primitivas de un equipo cuántico.  Hasta una determinada escala (número de qubits), la computación cuántica se puede simular en un equipo clásico. Con la simulación, puede empezar a escribir programas cuánticos hoy mismo para ejecutarlos en hardware cuántico mañana.  También hemos incluido ejemplos, bibliotecas y ejercicios de aprendizaje para que sea fácil empezar hoy mismo con la programación cuántica con Q#. 

## <a name="next-steps"></a>Pasos siguientes

* [¿Qué pueden hacer los equipos cuánticos?](xref:microsoft.quantum.overview.computers)
* [Introducción a Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
* Más información sobre los [conceptos de la computación cuántica](xref:microsoft.quantum.concepts.intro)
