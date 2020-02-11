---
uid: microsoft.quantum.welcome
title: Introducción al kit de desarrollo de Microsoft Quantum (QDK)
description: Más información sobre cómo empezar a usar el QDK.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: overview
ms.openlocfilehash: 066981e3e2fb468c1ff2a4cf4d3e7cff057772ab
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036345"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Introducción al kit de desarrollo de Microsoft Quantum (QDK)

Le damos la bienvenida al kit de desarrollo de Microsoft Quantum.  
El QDK contiene todas las herramientas que necesitará para compilar sus propios programas y experimentos cuánticos con Q#, un lenguaje de programación diseñado específicamente para el desarrollo de aplicaciones cuánticas. 

Para comenzar enseguida, vaya a la [guía de instalación del QDK](xref:microsoft.quantum.install).
Allí se le guiará por la instalación del kit de desarrollo de Microsoft Quantum en máquinas Windows, Linux o MacOS para que pueda escribir sus propios programas cuánticos.

Si no se siente preparado para empezar a codificar, pero quiere obtener más información acerca de la computación cuántica y Q#, le recomendamos que siga leyendo este artículo para conocer los recursos que tiene a su disposición. En la sección [Cinco preguntas sobre la computación cuántica](#five-questions-about-quantum-computing), encontrará vínculos a la información que necesita.

## <a name="get-started-programming"></a>Introducción a la programación

El kit de desarrollo de Microsoft Quantum proporciona muchas maneras de aprender a desarrollar un programa cuántico con Q#.
Para empezar a trabajar con la eficacia de la computación cuántica, pruebe nuestros *inicios rápidos*:

* El [generador de números cuánticos aleatorios](xref:microsoft.quantum.quickstarts.qrng) es una aplicación de Q# del estilo "Hola mundo", que proporciona una breve introducción a los conceptos cuánticos y permite compilar y ejecutar una aplicación cuántica en minutos.
* La guía [Aspectos básicos de la programación cuántica con Q#](xref:microsoft.quantum.write-program) contiene instrucciones para escribir un programa de Q# que muestra algunos de los conceptos básicos de la programación cuántica. 
    Si no está listo para empezar a codificar, puede seguir sin instalar QDK y obtener información general sobre el lenguaje de programación Q# y los primeros conceptos de la computación cuántica.
* El [algoritmo de búsqueda de Grover](xref:microsoft.quantum.quickstarts.search) ofrece un ejemplo de un programa de Q# para que se haga una idea de la capacidad de Q# para expresar el algoritmo cuántico de forma que abstraiga las operaciones cuánticas de bajo nivel. 
    Este inicio rápido le guía por el desarrollo del programa en diversos entornos de programación (con un host de Python o con el host de lenguaje de .NET y con Visual Studio o Visual Studio Code).

### <a name="learning-further"></a>Aprender más
* Si desea profundizar más en la programación con Q#, consulte [Quantum Katas](https://github.com/Microsoft/QuantumKatas), una colección de ejercicios de programación en Q# autoguiados que presentan la computación cuántica.
    Muchos de estos katas también están disponibles como cuadernos de Q#. 
* En el [repositorio de ejemplos](https://github.com/Microsoft/Quantum) hay varios ejemplos de cómo escribir programas cuánticos con Q#. La mayoría de estos ejemplos están escritos con nuestras [bibliotecas cuánticas](https://github.com/Microsoft/QuantumLibraries) de código abierto, incluidas las bibliotecas [estándar](xref:microsoft.quantum.libraries.standard.intro) y de [química](xref:microsoft.quantum.chemistry.concepts.intro) (más información a continuación).

## <a name="five-questions-about-quantum-computing"></a>Cinco preguntas sobre la computación cuántica

Si aún no tiene experiencia en computación cuántica, sabemos que puede parecer un poco desalentadora. Hemos recopilado recursos para ayudarle a empezar a aprender computación cuántica. Con la ayuda de estos breves artículos, estamos seguros de que podrá empezar a programar enseguida.
* [¿Qué es la computación cuántica?](xref:microsoft.quantum.overview.what)
* [¿Qué pueden hacer los equipos cuánticos?](xref:microsoft.quantum.overview.computers)
* [¿Por qué aprender computación cuántica?](xref:microsoft.quantum.overview.why)
* [¿Qué es Q#?](xref:microsoft.quantum.overview.qsharp)
* [Cómo aprender computación cuántica con Q#](xref:microsoft.quantum.overview.learn)

## <a name="quantum-development-kit-documentation"></a>Documentación del kit de desarrollo de Microsoft Quantum

La documentación actual incluye los temas adicionales siguientes.

### <a name="using-q"></a>Uso de Q#
* En [Técnicas de desarrollo cuántico](xref:microsoft.quantum.techniques.intro), se especifican los conceptos básicos que se usan para crear programas cuánticos en Q#. Los temas incluyen estructuras de archivos, operaciones y funciones, trabajo con qubits y algunos temas avanzados.
* En [Referencia del lenguaje Q#](xref:microsoft.quantum.language.intro), se detalla el lenguaje Q#, incluido el modelo de tipos, las expresiones, las instrucciones y el uso del compilador.
* En [Simuladores cuánticos y aplicaciones host](xref:microsoft.quantum.machines), se describe cómo se ejecutan los algoritmos cuánticos, qué máquinas cuánticas hay disponibles y cómo escribir un controlador que no sea de Q# para el programa cuántico.

### <a name="q-libraries"></a>Bibliotecas de Q#
* En [Bibliotecas estándar de Q#](xref:microsoft.quantum.libraries.standard.intro), se describen las operaciones y funciones que admiten los algoritmos cuánticos de Q# y el requisito de control del lenguaje clásico. 
    Entre los temas se incluyen flujo de control, estructuras de datos, corrección de errores, pruebas y depuración. 
* En [Biblioteca de química de Q#](xref:microsoft.quantum.chemistry.concepts.intro), se describen las operaciones y las funciones que admiten la simulación de química cuántica, una aplicación fundamental de la computación cuántica. Entre los temas se incluyen la simulación de la dinámica hamiltoniana y la estimación de la fase cuántica, entre otros.
* En [Biblioteca numérica de Q#](xref:microsoft.quantum.numerics.intro), se describen las operaciones y funciones que admiten la expresión de funciones aritméticas complejas en cuanto a operaciones nativas de las máquinas de destino.
* En [Referencia de las bibliotecas de Q#](xref:microsoft.quantum.standardlibsintro), se incluye información de referencia sobre las entidades de biblioteca por espacio de nombres.

### <a name="general-quantum-computing"></a>Computación cuántica general
* En [Conceptos de la computación cuántica](xref:microsoft.quantum.concepts.intro), se incluyen temas como la relevancia del álgebra lineal en la computación cuántica, la naturaleza y el uso de un qubit o cómo leer un circuito cuántico, entre otros.
* El [Glosario de la computación cuántica](xref:microsoft.quantum.glossary) es un glosario con algunos términos fundamentales específicos de la programación y computación cuántica. 
    Si no está familiarizado con el tema, puede ser una referencia útil mientras lee nuestra documentación.
* [Más información](xref:microsoft.quantum.more-information) contiene referencias seleccionadas especialmente para obtener información detallada sobre los temas de la computación cuántica.

### <a name="additional-info"></a>Información adicional
* [Notas de la versión del kit de desarrollo de Microsoft Quantum](xref:microsoft.quantum.relnotes).


## <a name="be-a-part-of-the-q-open-source-community"></a>Forme parte de la comunidad de código abierto de Q#
El kit de desarrollo de Microsoft Quantum es un kit de desarrollo de código abierto que permite a los desarrolladores hacer que la computación cuántica sea más accesible para todos para que podamos resolver algunos de los desafíos más apremiantes del mundo.  Las instituciones académicas que necesiten software de código abierto podrán implementar Q# con fines de aprendizaje y desarrollo cuántico. Con el kit de desarrollo de código abierto, los desarrolladores y expertos en el tema también tienen la oportunidad de aportar mejoras e ideas a través de su código.

Sus comentarios, participación y contribuciones al kit de desarrollo de Microsoft Quantum es importante.  Consulte [Contribución al kit de desarrollo de Microsoft Quantum](xref:microsoft.quantum.contributing) para obtener más información acerca de los orígenes del kit de desarrollo de Microsoft Quantum, enviar comentarios y averiguar cómo puede participar en las decisiones y contribuir a esta plataforma de desarrollo cuántico creciente.

Si desea más información general sobre la iniciativa de computación cuántica de Microsoft, consulte [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).
