---
title: Abrir solicitudes de incorporación de cambios
description: Obtenga información sobre cómo enviar una solicitud de incorporación de cambios de GitHub cuando esté listo para aportar código o documentación al Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: a4373a65688893c95e0475356c8f6fca0912f8c5
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907467"
---
# <a name="opening-pull-requests"></a>Apertura de solicitudes de incorporación de cambios #

Toda la documentación del kit de desarrollo de Quantum se administra mediante el sistema de control de versiones de Git mediante el uso de varios repositorios hospedados en GitHub.
El uso conjunto de Git y GitHub facilita la colaboración en el kit de desarrollo de Quantum.
En concreto, cualquier repositorio git se puede clonar o bifurcar para crear una copia completamente independiente de ese repositorio.
Esto le permite trabajar en su contribución con las herramientas y a la velocidad que prefiera.

Cuando esté listo, puede enviarnos una solicitud para incluir su contribución en nuestro repositorios, mediante la funcionalidad de _solicitud de incorporación_ de cambios de github.
La página de cada solicitud de incorporación de cambios incluye detalles de todos los cambios que hacen su contribución, una lista de comentarios sobre su contribución y un conjunto de herramientas de revisión que otros miembros de la comunidad pueden usar para proporcionar comentarios y consejos.

> [!NOTE]
> Aunque un tutorial completo sobre git está fuera del ámbito de esta guía, se pueden sugerir los siguientes vínculos para obtener más recursos sobre el aprendizaje de git:
>
> - [Aprenda git](https://www.atlassian.com/git): un conjunto de tutoriales de Git de Atlassian.
> - [Control de versiones en Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): una guía sobre cómo usar Visual Studio Code como una GUI para git.
> - [Laboratorio de aprendizaje de github](https://lab.github.com/): un conjunto de cursos en línea para el uso de Git, GitHub y tecnologías relacionadas.
> - [Visualización de Git](https://git-school.github.io/visualizing-git/): herramienta interactiva para visualizar cómo los comandos de Git cambian el estado de un repositorio.
> - [Control de versiones con git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): un tutorial de Git orientado hacia la informática científica.
> - [Obtenga información sobre la bifurcación de Git](https://learngitbranching.js.org/): un conjunto interactivo de la bifurcación y el reajuste de los rompecabezas para ayudar a conocer las nuevas características de Git.

## <a name="what-is-a-pull-request"></a>¿Qué es una solicitud de incorporación de cambios? ##

Una vez mencionado lo anterior, es útil dedicar unos minutos a indicar qué **es**una solicitud de incorporación de cambios.
Al trabajar con git, los cambios se representan como _confirmaciones_ que describen cómo se relacionan los cambios con el estado del repositorio antes de esos cambios.
A menudo se dibujan diagramas en los que las confirmaciones se dibujan como círculos con flechas de confirmaciones anteriores.

Supongamos que ha iniciado una contribución en una _rama_ llamada `feature`.
Después, la bifurcación de **Microsoft/Quantum** podría tener un aspecto similar al siguiente:

![Una rama de trabajo en GitHub](~/media/git-workflow-step0.png)

Si realiza cambios en el repositorio local, puede _extraer_ los cambios de otro repositorio en el suyo para detectar los cambios que se produjeron en el nivel ascendente.

![Extracción y combinación de cambios de un repositorio ascendente](~/media/git-workflow-step1.png)

Las solicitudes de incorporación de cambios funcionan de la misma manera, pero en orden inverso: cuando se abre una solicitud de incorporación de cambios, se solicita el repositorio ascendente para extraer su contribución.

![Solicitando volver a extraer los cambios en el repositorio original](~/media/git-workflow-step2.png)

Al abrir una solicitud de incorporación de cambios a uno de nuestros repositorios, GitHub ofrecerá una oportunidad para que otros usuarios de la comunidad puedan ver un resumen de los cambios, comentarlos y realizar sugerencias sobre cómo mejorar la contribución.

![Captura de pantalla de una solicitud de incorporación de cambios en GitHub](~/media/pull-request-header.png)

El uso de este proceso nos ayuda a usar la funcionalidad de GitHub para mejorar las contribuciones y para mantener un producto de alta calidad para la comunidad de programación de Quantum.

## <a name="how-to-make-a-pull-request"></a>Cómo crear una solicitud de incorporación de cambios ##

Hay dos formas principales de hacer una solicitud de incorporación de cambios.
En el caso de los cambios pequeños que solo afectan a un solo archivo, la interfaz Web de GitHub se puede usar para realizar una solicitud de incorporación de cambios completamente en línea.
En el caso de las contribuciones más complicadas, a menudo es más fácil usar el equipo local para preparar una solicitud de incorporación de cambios en primer lugar.

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a>Pasos siguientes ##

Enhorabuena por usar git para ayudar a la comunidad Quantum Development Kit.
Para obtener más información sobre cómo contribuir con el código, continúe con la siguiente guía.

> [!div class="nextstepaction"]
> [Obtener información sobre cómo colaborar en el código](xref:microsoft.quantum.contributing.code)
