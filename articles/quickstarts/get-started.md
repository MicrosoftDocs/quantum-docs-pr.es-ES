---
uid: microsoft.quantum.welcome
title: Introducción al kit de desarrollo de Microsoft Quantum (QDK)
description: Aprenda cómo empezar a programar proyectos cuánticos en Q# con el kit de desarrollo de Microsoft Quantum.
author: bradben
ms.author: bradben
ms.date: 5/10/2020
ms.topic: overview
ms.openlocfilehash: ff4a3dc829423525e18d89d5ed3d621079d1a524
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274200"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Introducción al kit de desarrollo de Microsoft Quantum (QDK)

Le damos la bienvenida al kit de desarrollo de Microsoft Quantum.  

El kit de desarrollo de Microsoft Quantum contiene todas las herramientas que necesitará para compilar sus propios programas y experimentos cuánticos con Q#, un lenguaje de programación diseñado específicamente para el desarrollo de aplicaciones cuánticas.

Para comenzar enseguida, vaya a la [guía de instalación del QDK](xref:microsoft.quantum.install).
Allí se le guiará por la instalación del kit de desarrollo de Microsoft Quantum en máquinas Windows, Linux o MacOS para que pueda escribir sus propios programas cuánticos.

Si no está familiarizado con la computación cuántica, revise la sección [Información general](xref:microsoft.quantum.overview.introduction) para más información sobre qué pueden hacer los equipos cuánticos y los aspectos básicos de la informática cuántica.

## <a name="get-started-programming"></a>Introducción a la programación

El kit de desarrollo de Microsoft Quantum proporciona muchas maneras de aprender a desarrollar un programa cuántico con Q#.
Para empezar a trabajar con la eficacia de la computación cuántica, pruebe nuestros tutoriales:

* [Generador de números cuánticos aleatorios](xref:microsoft.quantum.quickstarts.qrng): comience con aplicación de Q# del estilo "Hola mundo", que proporciona una breve introducción a los conceptos cuánticos y permite compilar y ejecutar una aplicación cuántica en minutos.
* [Exploración del entrelazamiento con Q#](xref:microsoft.quantum.write-program): este tutorial contiene instrucciones para escribir un programa de Q# que muestra algunos de los conceptos básicos de la programación cuántica.
    Si no está listo para empezar a codificar, puede seguir sin instalar QDK y obtener información general sobre el lenguaje de programación Q# y los primeros conceptos de la computación cuántica.
* [Algoritmo de búsqueda de Grover](xref:microsoft.quantum.quickstarts.search): examine este ejemplo de un programa de Q# para que se haga una idea de la capacidad de Q# para expresar el algoritmo cuántico de forma que abstraiga las operaciones cuánticas de bajo nivel.
    Este tutorial le guía por el desarrollo del programa como una aplicación de línea de comandos de Q# con Visual Studio o Visual Studio Code.

### <a name="learning-further"></a>Más información
* Los [módulos de Microsoft Learn sobre computación cuántica](https://docs.microsoft.com/learn/browse/?term=quantum) le ayudarán a dominar los conceptos principales a su ritmo. Para más información sobre los conceptos básicos de la creación de programas cuánticos con el QDK, consulte el [primer módulo](https://docs.microsoft.com/learn/modules/qsharp-create-first-quantum-development-kit/).
* Si desea profundizar más en la programación con Q#, consulte [Quantum Katas](https://github.com/Microsoft/QuantumKatas), una colección de ejercicios de programación en Q# autoguiados que presentan la computación cuántica.
    Muchos de estos katas también están disponibles como cuadernos de Q#. 
* En el [repositorio de ejemplos](https://github.com/Microsoft/Quantum) hay varios ejemplos de cómo escribir programas cuánticos con Q#. La mayoría de estos ejemplos están escritos con nuestras [bibliotecas cuánticas](https://github.com/Microsoft/QuantumLibraries) de código abierto, incluidas las bibliotecas [estándar](xref:microsoft.quantum.libraries.standard.intro) y de [química](xref:microsoft.quantum.chemistry.concepts.intro) (más información a continuación).

## <a name="key-concepts-for-quantum-computing"></a>Conceptos clave de la computación cuántica

Si aún no tiene experiencia en computación cuántica, sabemos que puede parecer un poco desalentadora. Estos conceptos clave están diseñados para ayudarle a entrar en el mundo cuántico y comprender en qué se diferencia la computación cuántica de la computación clásica.

* [Descripción de la computación cuántica](xref:microsoft.quantum.overview.understanding)
* [Simuladores y equipos cuánticos](xref:microsoft.quantum.overview.simulators)
* [¿Qué son el QDK y el lenguaje de programación Q#?](xref:microsoft.quantum.overview.q-sharp)
* [Álgebra lineal para la computación cuántica](xref:microsoft.quantum.overview.algebra)

## <a name="quantum-development-kit-documentation"></a>Documentación del kit de desarrollo de Microsoft Quantum

La documentación actual incluye los temas adicionales siguientes.

### <a name="q-developer-guides"></a>Guías para desarrolladores de Q#

* [En la guía del usuario de Q#](xref:microsoft.quantum.guide) se detallan los conceptos básicos que se usan para crear programas cuánticos en Q#.
* En [Simuladores cuánticos y aplicaciones host](xref:microsoft.quantum.machines), se describe cómo se ejecutan los algoritmos cuánticos, qué máquinas cuánticas hay disponibles y cómo escribir un controlador que no sea de Q# para el programa cuántico.

### <a name="q-libraries"></a>Bibliotecas de Q#

* En [Bibliotecas estándar de Q#](xref:microsoft.quantum.libraries.standard.intro), se describen las operaciones y funciones que admiten los algoritmos cuánticos de Q# y el requisito de control del lenguaje clásico. 
    Entre los temas se incluyen flujo de control, estructuras de datos, corrección de errores, pruebas y depuración. 
* En [Biblioteca de química de Q#](xref:microsoft.quantum.chemistry.concepts.intro), se describen las operaciones y las funciones que admiten la simulación de química cuántica, una aplicación fundamental de la computación cuántica. Entre los temas se incluyen la simulación de la dinámica hamiltoniana y la estimación de la fase cuántica, entre otros.
* En [Biblioteca numérica de Q#](xref:microsoft.quantum.numerics.intro), se describen las operaciones y funciones que admiten la expresión de funciones aritméticas complejas en cuanto a operaciones nativas de las máquinas de destino.
* En [Referencia de las bibliotecas de Q#](xref:microsoft.quantum.standardlibsintro), se incluye información de referencia sobre las entidades de biblioteca por espacio de nombres.

### <a name="general-quantum-computing"></a>Computación cuántica general

* En [Conceptos de la computación cuántica](xref:microsoft.quantum.concepts.intro), se incluyen temas como la relevancia del álgebra lineal en la computación cuántica, la naturaleza y el uso de un cúbit o cómo leer un circuito cuántico, entre otros.
* El [Glosario de la computación cuántica](xref:microsoft.quantum.glossary) es un glosario con algunos términos fundamentales específicos de la programación y computación cuántica.
    Si no está familiarizado con el tema, puede ser una referencia útil mientras lee nuestra documentación.
* [Más información](xref:microsoft.quantum.more-information) contiene referencias seleccionadas especialmente para obtener información detallada sobre los temas de la computación cuántica.

### <a name="additional-info"></a>Información adicional

* [Notas de la versión del kit de desarrollo de Microsoft Quantum](xref:microsoft.quantum.relnotes).


## <a name="be-a-part-of-the-q-open-source-community"></a>Forme parte de la comunidad de código abierto de Q#

El kit de desarrollo de Microsoft Quantum es un kit de desarrollo de código abierto que permite a los desarrolladores hacer que la computación cuántica sea más accesible para todos para que podamos resolver algunos de los desafíos más apremiantes del mundo.  Las instituciones académicas que necesiten software de código abierto podrán implementar Q# con fines de aprendizaje y desarrollo cuántico. Con el kit de desarrollo de código abierto, los desarrolladores y expertos en el tema también tienen la oportunidad de aportar mejoras e ideas a través de su código.

Sus comentarios, participación y contribuciones al kit de desarrollo de Microsoft Quantum son importantes.  Consulte [Contribución al kit de desarrollo de Microsoft Quantum](xref:microsoft.quantum.contributing) para obtener más información acerca de los orígenes del kit de desarrollo de Microsoft Quantum, enviar comentarios y averiguar cómo puede participar en las decisiones y contribuir a esta plataforma de desarrollo cuántico creciente.

Si desea más información general sobre la iniciativa de computación cuántica de Microsoft, consulte [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).