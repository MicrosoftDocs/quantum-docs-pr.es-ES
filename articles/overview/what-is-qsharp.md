---
title: ¿Qué es Q#?
description: Obtenga más información sobre Q#, un lenguaje de programación creado por Microsoft para desarrollar aplicaciones para equipos cuánticos.
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: e04d72bafe390ff5c79af408db1d9400754b06ce
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864294"
---
# <a name="what-is-q"></a>¿Qué es Q#?

Q# es un lenguaje de programación con características especiales de la computación cuántica.

Q# proporciona a los programadores cuánticos un marco que les permite centrarse en los algoritmos sin tener que preocuparse por detalles técnicos, como la optimización de secuencia de puertas o la implementación física de un equipo cuántico.

El lenguaje de programación Q# proporciona un intuitivo conjunto de tipos, operaciones y expresiones lógicas para desarrollar algoritmos sin tener que preocuparse por la lógica interna del equipo cuántico.

## <a name="code-algorithms"></a>Algoritmos de código

Al principio, los algoritmos de computación cuántica se visualizaban como diagramas, de forma similar a los diagramas de circuitos de la computación clásica.  Mientras que el modelo de circuitos se ha usado mucho en la investigación de computación cuántica durante muchos años, en Microsoft creemos que los desarrolladores pueden ir más allá de los circuitos cuánticos y desarrollar aplicaciones y algoritmos cuánticos con Q#. El lenguaje Q# se ha diseñado para aprovechar lo que hemos aprendido durante décadas de desarrollo de software clásico y capacita a los desarrolladores cuánticos con funcionalidades de lenguaje de alto nivel destinadas a la computación cuántica.

## <a name="how-does-q-work"></a>¿Cómo funciona Q#?

Uno de los bloques de compilación fundamentales de Q# es el tipo `Qubit`, que no se puede copiar ni acceder a él directamente, como un qubit real. En su lugar, podemos medirlo y almacenar el resultado de la medición en una variable `Result`, un tipo de Q# que puede tomar dos valores posibles: `Zero` y `One`. Construcciones como esta garantizan que los algoritmos respeten siempre las leyes de la física cuántica, así como que se puedan ejecutar correctamente en simuladores o equipos cuánticos.

Q# también incluye funcionalidades de lógica clásicas, como condicionales y bucles con algunos matices, para asegurarse de que se respetan todas las reglas cuánticas. Por ejemplo, restringir el modo en que se ejecutan los bucles para asegurarse de que no se llama a operaciones cuánticas en funciones que pueden contener solo subrutinas clásicas deterministas.

Con frecuencia, los programas de Q# están emparejados con un programa host escrito en C# o Python, que puede proporcionar una organización adecuada del código clásico y cuántico. Además de la compatibilidad con lenguajes como C# y Python, QDK proporciona compatibilidad de Jupyter Notebook con el kernel de Jupyter IQ#.

## <a name="use-q-to-learn-quantum-computing"></a>Uso de Q# para aprender computación cuántica

Hasta ahora, para aprender computación cuántica, necesitaba aprender el modelo de circuitos para entender los algoritmos como una forma de secuencias ordenadas de mediciones y puertas cuánticas. Con Q#, puede ir por otro camino: aprenda computación cuántica mediante la escritura de programas cuánticos.

## <a name="use-q-to-design-quantum-algorithms"></a>Uso de Q# para diseñar algoritmos cuánticos

Q# proporciona un creciente número de bibliotecas y tipos definidos por el usuario que le ayudarán a implementar herramientas y a crear algoritmos cuánticos avanzados. Por ejemplo, ¿necesita entrelazar q1 y q2 de dos qubits? En lugar de aplicar las puertas necesarias de forma individual para obtener los qubits entrelazados, puede usar la operación `PrepareEntangledState([q1], [q2])` ya integrada.

## <a name="use-q-to-estimate-quantum-resources"></a>Uso de Q# para calcular los recursos cuánticos

Puede simular la ejecución del programa de Q# con el simulador cuántico de estado completo incluido en Quantum Development Kit (QDK).  QDK también ofrece estimaciones de recursos que proporcionan información sobre el rendimiento de los programas de Q# que son demasiado grandes para ejecutarse en un simulador.  Esto resulta muy útil para los diseñadores de algoritmos, porque pueden optimizar sus programas para que usen menos recursos (por ejemplo, un menor número de qubits que se ejecutan para menos cantidad de operaciones), para que puedan ejecutarse en un hardware cuántico de menor escala.

## <a name="use-q-to-validate-hardware-performance"></a>Uso de Q# para validar el rendimiento del hardware

Lo interesante de Q# es que un programa puede escribirse una vez y ejecutarse en simuladores cuánticos para depuración, y ejecutarse en equipos cuánticos con distinto hardware.  Se pueden ejecutar programas de pruebas comparativas escritos en Q# para validar el rendimiento del hardware y comparar los resultados a medida que los equipos cuánticos evolucionen y haya nuevos equipos cuánticos disponibles.  

## <a name="next-steps"></a>Pasos siguientes

* [¿Cómo puedo aprender computación cuántica?](xref:microsoft.quantum.overview.learn)
* [Introducción a Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
