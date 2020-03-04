---
title: ¿Qué son Q# y QDK?
description: Obtenga más información sobre Q#, un lenguaje de programación creado por Microsoft para desarrollar aplicaciones para equipos cuánticos, y componente clave del kit de desarrollo de Microsoft Quantum.
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907008"
---
# <a name="what-are-q-and-the-qdk"></a>¿Qué son Q# y QDK?

Q# es un lenguaje de programación con características diseñadas específicamente para su uso con la computación cuántica.
Es un componente clave del kit de desarrollo de Microsoft Quantum (QDK) y proporciona a los programadores cuánticos un entorno que les permite centrarse en los algoritmos sin tener que preocuparse por detalles técnicos, como la optimización de secuencias de puertas o la implementación física de un equipo cuántico.

QDK incluye numerosas herramientas que proporcionan a los desarrolladores todo lo que necesitan para empezar a escribir programas cuánticos.
Además del lenguaje Q#, el QDK incluye:
* Las *bibliotecas de Q#* , que permiten a los desarrolladores empezar a crear aplicaciones cuánticas rápidamente.
* Varias *máquinas de destino* en las que pueden ejecutar los programas de Q#. Entre ellas se incluyen estimadores y simuladores de recursos para programas cuánticos más grandes, así como un simulador cuántico de estado completo que se comporta como un equipo cuántico sin ruido. Esta última es muy útil para probar nuevas ideas, depurar programas y obtener información sobre la física cuántica, pero solo es eficaz para programas con relativamente pocos qubits. Estamos deseando poder hacer que, en el futuro, haya hardware de computación cuántica como máquinas de destino.
* *Herramientas* para que el trabajo con Q# sea lo más sencillo posible, como extensiones para Visual Studio y VS Code, y paquetes para usar con Python y Jupyter Notebook.
* *Documentación de API* para emparejar Q# con los lenguajes de host clásico, como Python y C#.

Las aplicaciones desarrolladas con el kit de desarrollo de Microsoft Quantum constan de dos partes:
1. Uno o más algoritmos cuánticos, que se implementan con el lenguaje de programación cuántica Q# y se llaman con el programa de host clásico. Se componen de: 
    - Operaciones de Q#: subrutinas que contienen operaciones cuánticas. 
    - Funciones de Q#: subrutinas clásicas que se usan en el algoritmo cuántico.
2. Un programa clásico, implementado en un lenguaje de programación clásico como Python o C#, que actúa como punto de entrada principal e invoca operaciones de Q# cuando quiere ejecutar un algoritmo cuántico.

## <a name="write-quantum-programs-not-quantum-circuits"></a>Escritura de programas cuánticos, no circuitos cuánticos

Al principio, los algoritmos de computación cuántica se visualizaban como diagramas, de forma similar a los diagramas de circuitos de la computación clásica.
Mientras que el modelo de circuitos se ha usado mucho en la investigación de computación cuántica durante muchos años, en Microsoft creemos que los desarrolladores pueden ir más allá de los circuitos cuánticos y desarrollar aplicaciones y algoritmos cuánticos con Q#.
El lenguaje Q# se ha diseñado para aprovechar lo que hemos aprendido durante décadas de desarrollo de software clásico y capacita a los desarrolladores cuánticos con funcionalidades de lenguaje de alto nivel destinadas a la computación cuántica.

## <a name="how-does-q-work"></a>¿Cómo funciona Q#?

El lenguaje de programación Q# proporciona un intuitivo conjunto de tipos, operaciones y expresiones lógicas para desarrollar algoritmos sin tener que preocuparse por la lógica interna del equipo cuántico.

Uno de los bloques de compilación fundamentales de Q# es el tipo `Qubit`, que no se puede copiar ni acceder a él directamente, como un qubit real.
En su lugar, podemos medirlo y almacenar el resultado de la medición en una variable `Result`, un tipo de Q# que puede tomar dos valores posibles: `Zero` y `One`.
Construcciones como esta garantizan que los algoritmos respeten siempre las leyes de la física cuántica, así como que se puedan ejecutar correctamente en simuladores o equipos cuánticos.

Q# también incluye funcionalidades de lógica clásicas, como condicionales y bucles con algunos matices, para asegurarse de que se respetan todas las reglas cuánticas.
Por ejemplo, restringir el modo en que se ejecutan los bucles para asegurarse de que no se llama a operaciones cuánticas en funciones que pueden contener solo subrutinas clásicas deterministas.

Con frecuencia, los programas de Q# están emparejados con un programa host escrito en C# o Python, que puede proporcionar una organización adecuada del código clásico y cuántico.
Además de la compatibilidad con lenguajes como C# y Python, QDK proporciona compatibilidad de Jupyter Notebook con el kernel de Jupyter IQ#.

## <a name="what-can-i-use-q-for"></a>¿Para qué puedo usar Q#?

### <a name="use-q-to-learn-quantum-computing"></a>Uso de Q# para aprender computación cuántica

Hasta ahora, para aprender computación cuántica, necesitaba aprender el modelo de circuitos para entender los algoritmos como una forma de secuencias ordenadas de mediciones y puertas cuánticas. Con Q#, puede ir por otro camino: aprenda computación cuántica mediante la escritura de programas cuánticos.

### <a name="use-q-to-design-quantum-algorithms"></a>Uso de Q# para diseñar algoritmos cuánticos

Q# proporciona un creciente número de bibliotecas y tipos definidos por el usuario que le ayudarán a implementar herramientas y a crear algoritmos cuánticos avanzados. Por ejemplo, ¿necesita entrelazar q1 y q2 de dos qubits? En lugar de aplicar las puertas necesarias de forma individual para obtener los qubits entrelazados, puede usar la operación `PrepareEntangledState([q1], [q2])` ya integrada.

### <a name="use-q-to-estimate-quantum-resources"></a>Uso de Q# para calcular los recursos cuánticos

Puede simular la ejecución del programa de Q# con el simulador cuántico de estado completo incluido en Quantum Development Kit (QDK).  QDK también ofrece estimaciones de recursos que proporcionan información sobre el rendimiento de los programas de Q# que son demasiado grandes para ejecutarse en un simulador.  Esto resulta muy útil para los diseñadores de algoritmos, porque pueden optimizar sus programas para que usen menos recursos (por ejemplo, un menor número de qubits que se ejecutan para menos cantidad de operaciones), para que puedan ejecutarse en un hardware cuántico de menor escala.

### <a name="use-q-to-validate-hardware-performance"></a>Uso de Q# para validar el rendimiento del hardware

Lo interesante de Q# es que un programa puede escribirse una vez y ejecutarse en simuladores cuánticos para depuración, y ejecutarse en equipos cuánticos con distinto hardware.  Se pueden ejecutar programas de pruebas comparativas escritos en Q# para validar el rendimiento del hardware y comparar los resultados a medida que los equipos cuánticos evolucionen y haya nuevos equipos cuánticos disponibles.  

## <a name="next-steps"></a>Pasos siguientes

* [Cómo aprender computación cuántica](xref:microsoft.quantum.overview.learn)
* [Introducción a Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
