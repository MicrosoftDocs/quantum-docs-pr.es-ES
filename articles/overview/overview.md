---
title: Introducción a la computación cuántica
description: Aprenda qué es la computación cuántica, que pueden hacer los equipos cuánticos y cómo puede aprender computación cuántica.
author: bradben
ms.author: bradben
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
no-loc:
- Q#
- $$v
ms.openlocfilehash: 59cb595ac207d6e84358fc6ba742e0e0019c76f9
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866985"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a>Introducción a la computación cuántica y el kit de desarrollo de Microsoft Quantum

El kit de desarrollo de Microsoft Quantum (QDK) es un conjunto de herramientas de código abierto diseñadas para ayudar a los desarrolladores a aprender algoritmos cuánticos y a escribir programas cuánticos. La computación cuántica ofrece la posibilidad de resolver algunos de los mayores desafíos del planeta en las áreas de medioambiente, agricultura, salud, energía, clima, ciencia de los materiales, y problemas que aún no se han imaginado siquiera.  

En algunas de estas cuestiones, incluso nuestros equipos más potentes tienen problemas. Aunque estamos notando solo los primeros efectos de la tecnología cuántica en la informática, podría llegar muy lejos y cambiar nuestra percepción de la computación.

## <a name="what-is-quantum-computing"></a>¿Qué es la computación cuántica?

En su uso moderno, la palabra cuanto designa la unidad más pequeña posible de cualquier propiedad física, normalmente en referencia a las propiedades de partículas atómicas o subatómicas. Como unidades de procesamiento, los equipos cuánticos usan partículas cuánticas reales, átomos artificiales o propiedades colectivas de partículas cuánticas, y son dispositivos grandes, complejos y caros.

Cuando aplicamos el comportamiento único de la física cuántica a la computación, los equipos cuánticos introducen nuevos conceptos en los métodos de programación tradicionales y utilizan comportamientos físicos cuánticos como la superposición, el entrelazamiento y la interferencia cuántica.

## <a name="what-can-a-quantum-computer-do"></a>¿Qué pueden hacer los equipos cuánticos?

Un equipo cuántico no es un superequipo que pueda hacer todo con más rapidez, pero hay algunas áreas en las que los equipos cuánticos destacan.

- [Simulación cuántica](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [Criptografía](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [Búsqueda](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [Optimización](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization):
- [Aprendizaje automático](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a>Simulación cuántica

Como los equipos cuánticos usan fenómenos cuánticos en la computación, son adecuados para el modelado de otros sistemas cuánticos. La fotosíntesis, la superconductividad y las formaciones moleculares complejas son ejemplos de mecanismos cuánticos que los programas cuánticos pueden simular.

## <a name="cryptography-and-shors-algorithm"></a>Criptografía y algoritmo de Shor

En 1994, Peter Shor mostró que un equipo cuántico escalable podría desbloquear las técnicas de cifrado de uso generalizado, como el algoritmo de RSA. La criptografía clásica se basa en la irresolubilidad de problemas como la factorización de enteros o los logaritmos discretos, muchos de los cuales se pueden resolver de forma más eficaz con equipos cuánticos.

## <a name="search-and-grovers-algorithm"></a>Búsquedas y algoritmo de Grover

En 1996, Lov Grover desarrolló un algoritmo cuántico que aceleró drásticamente la solución a las búsquedas de datos no estructurados y permitía ejecutar las búsquedas en menos pasos que cualquier algoritmo clásico.

## <a name="quantum-inspired-computing-and-optimization"></a>Optimización y computación de inspiración cuántica

Los algoritmos de inspiración cuántica usan principios cuánticos para aumentar la velocidad y la precisión, pero se implementan con software clásico. Este enfoque permite a los desarrolladores aprovechar la eficacia de las nuevas técnicas cuánticas hoy sin tener que esperar al hardware cuántico, que sigue siendo un sector emergente.

La optimización es el proceso de encontrar la mejor solución para un problema, según el resultado deseado y las restricciones existentes. Factores como el costo, la calidad o el tiempo de producción juegan un papel crítico en las decisiones tomadas por la industria y la ciencia. Los algoritmos de optimización de inspiración cuántica que se ejecutan en los equipos clásicos de hoy en día permiten encontrar soluciones que hasta ahora no eran posibles. Además de optimizar el flujo del tráfico para reducir la congestión, podemos hablar de asignación de puertas a un avión, entrega de paquetes, programación de trabajos y mucho más. Con los avances en la ciencia de los materiales, habrá nuevas formas de energía, baterías con mayor capacidad y materiales más duraderos y ligeros.

> [!NOTE]
> Obtenga más información sobre cómo se usa computación de inspiración cuántica de Microsoft en la [ciencia de los materiales](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/), la [administración de riesgos](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/) y la [medicina](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/).

## <a name="quantum-machine-learning"></a>Aprendizaje automático cuántico

El aprendizaje automático en equipos clásicos está revolucionando el mundo de la ciencia y la empresa. Sin embargo, el alto costo computacional de entrenar los modelos dificulta el desarrollo y el alcance de este campo. El área del aprendizaje automático cuántico explora cómo diseñar e implementar software cuántico que permita el aprendizaje automático con una ejecución más rápida que en los equipos clásicos.

El kit de desarrollo de Microsoft Quantum incluye la [biblioteca de aprendizaje automático cuántico](xref:microsoft.quantum.machine-learning.concepts.intro), que ofrece la posibilidad de ejecutar experimentos de aprendizaje automático híbridos cuánticos-clásicos. La biblioteca incluye ejemplos y tutoriales, y ofrece las herramientas necesarias para implementar un nuevo algoritmo híbrido cuántico-clásico, el clasificador cuántico centrado en el circuito, para solucionar problemas de clasificación supervisada.

## <a name="no-locq-and-the-microsoft-quantum-development-kit-qdk"></a>Q# y el kit de desarrollo de Microsoft Quantum (QDK)

Q# es el lenguaje de programación de código abierto de Microsoft para desarrollar y ejecutar algoritmos cuánticos. Forma parte de [QDK](https://docs.microsoft.com/quantum/), un kit de desarrollo completo para Q#que puede usar con herramientas y lenguajes estándar para desarrollar aplicaciones cuánticas que puede ejecutar en varios entornos, e integra el simulador cuántico de estado completo.

Hay extensiones para Visual Studio y VS Code, y paquetes para su uso con Python y Jupyter Notebook.

QDK incluye una biblioteca estándar, además de bibliotecas especializadas de química, aprendizaje automático y valores numéricos.

La documentación incluye una guía del lenguaje Q#, tutoriales y código de ejemplo para empezar a trabajar rápidamente, así como artículos completos que le ayudarán a profundizar en los conceptos de la informática cuántica.  

## <a name="microsoft-quantum-hardware-partners"></a>Asociados de hardware cuántico de Microsoft

Microsoft se ha asociado con compañías de hardware cuántico para proporcionar a los desarrolladores acceso en la nube a hardware cuántico. Con el uso de la plataforma [Azure Quantum](https://azure.microsoft.com/services/quantum/) y el lenguaje Q#, los desarrolladores podrán explorar los algoritmos cuánticos y ejecutar sus programas cuánticos en diferentes tipos de hardware cuántico.

Tanto [IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) como [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) utilizan procesadores de **trampa de iones**, que utilizan iones individuales atrapados en un campo electrónico, mientras que [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) usa circuitos superconductores.

## <a name="next-steps"></a>Pasos siguientes

[Conceptos clave de la computación cuántica](xref:microsoft.quantum.overview.understanding)
[Inicios rápidos](xref:microsoft.quantum.welcome)