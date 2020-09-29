---
title: ¿Qué son el QDK y el lenguaje de programación Q#?
description: Obtenga información sobre el kit de desarrollo de Microsoft Quantum, el lenguaje de programación Q# y cómo puede crear programas cuánticos.
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 21adfcc1c5321d87665adb39a3c838bbda0b8861
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834574"
---
# <a name="what-are-the-no-locq-programming-language-and-qdk"></a>¿Qué son el QDK y el lenguaje de programación Q#?

Q# es el lenguaje de programación de código abierto de Microsoft para desarrollar y ejecutar algoritmos cuánticos. Forma parte del kit de desarrollo de Microsoft Quantum (QDK), que incluye [bibliotecas de Q#](xref:microsoft.quantum.libraries), [simuladores cuánticos](xref:microsoft.quantum.machines), [extensiones para otros entornos de programación](xref:microsoft.quantum.install) y [documentación de API](xref:microsoft.quantum.apiref-intro). Además de la biblioteca de Q# estándar, el QDK incluye bibliotecas de química, aprendizaje automático y valores numéricos.

Como lenguaje de programación, Q# dibuja elementos conocidos de Python, C# y F#, y admite un modelo de procedimientos básico para escribir programas con bucles, instrucciones if/then y tipos de datos comunes. También presenta nuevas operaciones y estructuras de datos específicas de la computación cuántica.

## <a name="what-can-i-do-with-the-qdk"></a>¿Qué puedo hacer con el QDK?

QDK es un kit de desarrollo completo de Q# que se puede usar con herramientas y lenguajes comunes para desarrollar aplicaciones cuánticas que puede ejecutar en diversos entornos. Los programas de Q# se pueden ejecutar como una aplicación de consola mediante Jupyter Notebook, o se puede usar un programa host de Python o .NET.

### <a name="develop-in-common-tools-and-environments"></a>Desarrollo en herramientas y entornos comunes

Integre el desarrollo cuántico con [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone) y [Jupyter Notebook](xref:microsoft.quantum.install.jupyter). Use las API integradas para emparejar los programas con los lenguajes host [Python](xref:microsoft.quantum.install.python) y [.NET](xref:microsoft.quantum.install.cs).

### <a name="try-quantum-operations-and-domain-specific-libraries"></a>Prueba de operaciones cuánticas y bibliotecas específicas del dominio

Escriba y pruebe los algoritmos cuánticos para explorar la superposición, el entrelazamiento y otras operaciones cuánticas. Las bibliotecas de Q# permiten ejecutar operaciones cuánticas complejas sin tener que diseñar secuencias de operaciones muy detalladas.

### <a name="run-programs-in-simulators"></a>Ejecución de programas en simuladores

Ejecute los programas cuánticos en un simulador cuántico de estado completo o un simulador de Toffoli de ámbito limitado, o bien pruebe el código de Q# en diferentes estimadores de recursos. 

## <a name="where-can-i-learn-more"></a>¿Dónde puedo obtener más información?

|||
| ---- | ---- |
| **Soy nuevo en la computación cuántica** | Revise algunos aspectos básicos de la física y la computación cuánticas en [Conceptos clave](xref:microsoft.quantum.overview.understanding).|
| **Quiero profundizar más en el lenguaje Q#** | Explore los tipos, las expresiones, las variables y la estructura de los programas cuánticos en la [guía de usuario de Q#](xref:microsoft.quantum.guide).|
| **Quiero empezar a escribir programas cuánticos** | Configure el entorno de Q# y empiece a escribir programas cuánticos con los [inicios rápidos](xref:microsoft.quantum.install).|

## <a name="how-does-no-locq-work"></a>¿Cómo funciona Q#?

Un programa de Q# puede compilarse en una aplicación independiente o se puede llamar desde un programa host escrito en Python o .NET.

Al compilar y ejecutar el programa, se crea una instancia del simulador cuántico, a la que se le pasa el código de Q#. El simulador utiliza el código de Q# para crear cúbits (simulaciones de partículas cuánticas) y aplicar transformaciones para modificar su estado. Después, los resultados de las operaciones cuánticas del simulador se devuelven al programa.  

Al aislar el código de Q# en el simulador, se garantiza que los algoritmos sigan las leyes de la física cuántica y que se puedan ejecutar correctamente en los equipos cuánticos.

![Flujo de código de Qsharp](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a>¿Cómo se usa el QDK?

Todo lo que necesita para escribir y ejecutar programas de Q#, incluido el compilador de Q#, las bibliotecas de Q# y los simuladores cuánticos, se puede instalar y ejecutar en el equipo local. En algún momento podrá ejecutar los programas de Q# de forma remota en un equipo cuántico real pero, hasta entonces, los simuladores cuánticos que se proporcionan con el QDK ofrecen resultados precisos y confiables.

- Desarrollar [aplicaciones de Q#](xref:microsoft.quantum.install.standalone) es la forma más rápida de empezar a trabajar.

- Ejecute [Jupyter Notebook con IQ#](xref:microsoft.quantum.install.jupyter), una extensión de Jupyter para compilar, simular y visualizar programas de Q#.

- Si está familiarizado con [Python](xref:microsoft.quantum.install.python), puede usarlo como plataforma de programación host para comenzar. El uso de Python está muy generalizado no solo entre desarrolladores, sino también científicos, investigadores y profesores.

- Si ya tiene experiencia con [C#, F# o VB.NET](xref:microsoft.quantum.install.cs) y está familiarizado con el entorno de desarrollo de Visual Studio, solo tendrá que agregar algunas extensiones a Visual Studio para prepararlo para Q#.  

## <a name="summary"></a>Resumen

Q# es un lenguaje de programación de código abierto para desarrollar programas cuánticos. Tiene bibliotecas que permiten crear operaciones cuánticas complejas y simuladores cuánticos para ejecutar y probar sus programas con precisión. Los programas de Q# pueden ejecutarse como aplicaciones independientes o se pueden llamar desde un programa host de Python o .NET, y se pueden escribir, ejecutar y probar en el equipo local.

## <a name="next-steps"></a>Pasos siguientes

[Álgebra lineal para la computación cuántica](xref:microsoft.quantum.overview.algebra)
