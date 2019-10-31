---
title: Contribución a Quantum Development Kit | Microsoft Docs
description: Contribución a Quantum Development Kit
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
ms.openlocfilehash: 4be86c5045ece62ae3af40090a2cd344d965e65f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73057404"
---
# <a name="contributing-to-the-quantum-development-kit"></a>Contribución a Quantum Development Kit #

Quantum Development Kit es más que una colección de herramientas para escribir programas cuánticos.
Forma parte de una amplia comunidad de personas que detectan la computación cuántica, realizan investigación en algoritmos cuánticos, desarrollan aplicaciones nuevas para dispositivos cuánticos y, de cualquier otro modo, trabajan para aprovechar al máximo la programación cuántica.
Como miembro de esa comunidad, Quantum Development Kit se propone ofrecer a los desarrolladores cuánticos las características que necesitan a través de una amplia variedad de conocimientos.
Sus contribuciones a Quantum Development Kit lo ayudarán a lograr ese objetivo mejorando las herramientas usadas por otros desarrolladores cuánticos, cómo se documentan esas herramientas e, incluso, mediante la creación de nuevas características y funcionalidades que ayuden a que toda la comunidad de programación cuántica sea un lugar mejor para la detección y la creación.
Estamos muy agradecidos por contribuciones y por la oportunidad de trabajar en conjunto para que nuestra comunidad sea lo mejor que pueda ser.

En esta guía, proporcionamos consejos sobre cómo su contribución puede ser lo más útil posible para la cada vez más amplia comunidad de programación cuántica.

## <a name="building-community"></a>Construcción de la comunidad ##

Lo primero que se debe hacer al realizar una contribución es considerar siempre con qué comunidad se colabora.
Al actuar de manera respetuosa y profesional con respecto a sus pares de la comunidad de programación cuántica y más, puede garantizar que sus esfuerzos creen la mejor y más acogedora comunidad posible.

Como parte de ese esfuerzo, todos los proyectos de Quantum Development Kit han adoptado el [Código de conducta de código abierto de Microsoft](https://opensource.microsoft.com/codeofconduct/).
Para más información, consulte las [preguntas más frecuentes sobre el código de conducta](https://opensource.microsoft.com/codeofconduct/faq/) o póngase en contacto con [opencode@microsoft.com](mailto:opencode@microsoft.com) si tiene cualquier otra pregunta o comentario.

## <a name="what-kinds-of-contributions-help-the-community"></a>¿Qué tipos de contribuciones ayudan a la comunidad? ##

Hay muchas formas distintas de ayudar a la comunidad de programación cuántica a través de sus contribuciones.
En esta guía, nos centraremos en tres de ellas que son especialmente pertinentes a Quantum Development Kit.
Todas estas formas son críticas para crear una comunidad cuántica que empodere a los usuarios.
Dicho esto, esta no es una lista completa, así es que lo invitamos a explorar otras formas de ayudar a la comunidad a basarse en la promesa de la programación cuántica.

- **Informe de errores.** El primer paso para corregir errores y otros tipos de problemas es identificarlos. Si encontró un error en Quantum Development Kit, nos gustaría que nos ayude a corregirlo y a crear un mejor conjunto de herramientas para la comunidad de programación cuántica.
- **Mejora de la documentación.** Todo conjunto de documentación puede ser mejor, puede abarcar más detalles y ser más accesible.
- **Contribuir con código.** Por supuesto, una de las formas de contribución más directa es agregando código nuevo a Quantum Development Kit.

Estos distintos tipos de contribuciones son enormemente valiosos y muy apreciados.
En el resto de la guía, ofreceremos consejos sobre cómo hacer cada tipo de contribución.

## <a name="where-do-contributions-go"></a>¿Adónde van las contribuciones? ##

Quantum Development Kit incluye una serie de partes distintas que funcionan en conjunto para obtener una plataforma para escribir programas cuánticos.
Cada una de estas partes diferentes encuentra su lugar en un repositorio distinto, por lo que una de las primeras cosas que se deben ordenar es el lugar al que pertenece cada contribución.

- [**microsoft/Quantum**](https://github.com/Microsoft/Quantum): ejemplos y herramientas para empezar a usar Quantum Development Kit.
- [**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries): bibliotecas estándar y específicas del dominio para Quantum Development Kit.
- [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas): ejercicios de programación autodirigidos para aprender la computación cuántica y el lenguaje de programación Q#.
- [**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler): el compilador Q#, la extensión de Visual Studio y la extensión de Visual Studio Code.
- [**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime): marco de simulación, generación de código y máquinas de destino de simulación para Quantum Development Kit.
- [**microsoft/iqsharp**](https://github.com/microsoft/iqsharp): funcionalidad de host de Python y kernel de Jupyter para Q#, así como imágenes de Docker para usar IQ# en entornos de nube.
- [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr): código fuente para la documentación publicada en https://docs.microsoft.com/quantum.

> [!NOTE]
> Lamentablemente, por el momento no podemos aceptar contribuciones de código y documentación en el repositorio [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC), pero de todos modos apreciamos los informes de errores.

También hay algunos otros repositorios más especializados que se centran en eventos diferentes o en una funcionalidad auxiliar relacionada con Quantum Development Kit.

- [**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty): compatibilidad del formato LaTex con la sintaxis de Q#.
- [**msr-quarc/intern-workshop-2019**](https://github.com/msr-quarc/intern-workshop-2019): tutorial de IQ# Notebook para Deutsch–Jozsa del taller para practicantes de 2019.

## <a name="next-steps"></a>Pasos siguientes ##

Gracias por formar parte de la comunidad de Quantum Development Kit. Nos complace recibir sus contribuciones.
Si desea obtener más información sobre las contribuciones, continúe con una de las siguientes guías.

> [!div class="nextstepaction"]
> [Aprenda a informar errores](xref:microsoft.quantum.contributing.reporting).

> [!div class="nextstepaction"]
> [Aprenda a contribuir con documentación](xref:microsoft.quantum.contributing.docs).

> [!div class="nextstepaction"]
> [Aprenda a abrir solicitudes de incorporación de cambios](xref:microsoft.quantum.contributing.pulls).

