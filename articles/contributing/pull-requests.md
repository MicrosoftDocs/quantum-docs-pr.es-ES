---
title: Abriendo solicitudes de incorporación de cambios | Microsoft Docs
description: Abrir solicitudes de incorporación de cambios
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: d70a0a0319d14cfdae4910b897733d77b236f2f9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183733"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="6c46f-103">Abrir solicitudes de incorporación de cambios</span><span class="sxs-lookup"><span data-stu-id="6c46f-103">Opening Pull Requests</span></span> #

<span data-ttu-id="6c46f-104">Toda la documentación del kit de desarrollo de Quantum se administra mediante el sistema de control de versiones de Git mediante el uso de varios repositorios hospedados en GitHub.</span><span class="sxs-lookup"><span data-stu-id="6c46f-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="6c46f-105">El uso conjunto de Git y GitHub facilita la colaboración en el kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="6c46f-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="6c46f-106">En concreto, cualquier repositorio git se puede clonar o bifurcar para crear una copia completamente independiente de ese repositorio.</span><span class="sxs-lookup"><span data-stu-id="6c46f-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="6c46f-107">Esto le permite trabajar en su contribución con las herramientas y a la velocidad que prefiera.</span><span class="sxs-lookup"><span data-stu-id="6c46f-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="6c46f-108">Cuando esté listo, puede enviarnos una solicitud para incluir su contribución en nuestro repositorios, mediante la funcionalidad de _solicitud de incorporación_ de cambios de github.</span><span class="sxs-lookup"><span data-stu-id="6c46f-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="6c46f-109">La página de cada solicitud de incorporación de cambios incluye detalles de todos los cambios que hacen su contribución, una lista de comentarios sobre su contribución y un conjunto de herramientas de revisión que otros miembros de la comunidad pueden usar para proporcionar comentarios y consejos.</span><span class="sxs-lookup"><span data-stu-id="6c46f-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="6c46f-110">Aunque un tutorial completo sobre git está fuera del ámbito de esta guía, se pueden sugerir los siguientes vínculos para obtener más recursos sobre el aprendizaje de git:</span><span class="sxs-lookup"><span data-stu-id="6c46f-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="6c46f-111">[Aprenda git](https://www.atlassian.com/git): un conjunto de tutoriales de Git de Atlassian.</span><span class="sxs-lookup"><span data-stu-id="6c46f-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="6c46f-112">[Control de versiones en Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): una guía sobre cómo usar Visual Studio Code como una GUI para git.</span><span class="sxs-lookup"><span data-stu-id="6c46f-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="6c46f-113">[Laboratorio de aprendizaje de github](https://lab.github.com/): un conjunto de cursos en línea para el uso de Git, GitHub y tecnologías relacionadas.</span><span class="sxs-lookup"><span data-stu-id="6c46f-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="6c46f-114">[Visualización de Git](https://git-school.github.io/visualizing-git/): herramienta interactiva para visualizar cómo los comandos de Git cambian el estado de un repositorio.</span><span class="sxs-lookup"><span data-stu-id="6c46f-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="6c46f-115">[Control de versiones con git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): un tutorial de Git orientado hacia la informática científica.</span><span class="sxs-lookup"><span data-stu-id="6c46f-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="6c46f-116">[Obtenga información sobre la bifurcación de Git](https://learngitbranching.js.org/): un conjunto interactivo de la bifurcación y el reajuste de los rompecabezas para ayudar a conocer las nuevas características de Git.</span><span class="sxs-lookup"><span data-stu-id="6c46f-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="6c46f-117">¿Qué es una solicitud de incorporación de cambios?</span><span class="sxs-lookup"><span data-stu-id="6c46f-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="6c46f-118">Una vez mencionado lo anterior, es útil dedicar unos minutos a indicar qué **es**una solicitud de incorporación de cambios.</span><span class="sxs-lookup"><span data-stu-id="6c46f-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="6c46f-119">Al trabajar con git, los cambios se representan como _confirmaciones_ que describen cómo se relacionan los cambios con el estado del repositorio antes de esos cambios.</span><span class="sxs-lookup"><span data-stu-id="6c46f-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="6c46f-120">A menudo se dibujan diagramas en los que las confirmaciones se dibujan como círculos con flechas de confirmaciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="6c46f-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="6c46f-121">Supongamos que ha iniciado una contribución en una _rama_ llamada `feature`.</span><span class="sxs-lookup"><span data-stu-id="6c46f-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="6c46f-122">Después, la bifurcación de **Microsoft/Quantum** podría tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="6c46f-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![](~/media/git-workflow-step0.png)

<span data-ttu-id="6c46f-123">Si realiza cambios en el repositorio local, puede _extraer_ los cambios de otro repositorio en el suyo para detectar los cambios que se produjeron en el nivel ascendente.</span><span class="sxs-lookup"><span data-stu-id="6c46f-123">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![](~/media/git-workflow-step1.png)

<span data-ttu-id="6c46f-124">Las solicitudes de incorporación de cambios funcionan de la misma manera, pero en orden inverso: cuando se abre una solicitud de incorporación de cambios, se solicita el repositorio ascendente para extraer su contribución.</span><span class="sxs-lookup"><span data-stu-id="6c46f-124">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![](~/media/git-workflow-step2.png)

<span data-ttu-id="6c46f-125">Al abrir una solicitud de incorporación de cambios a uno de nuestros repositorios, GitHub ofrecerá una oportunidad para que otros usuarios de la comunidad puedan ver un resumen de los cambios, comentarlos y realizar sugerencias sobre cómo mejorar la contribución.</span><span class="sxs-lookup"><span data-stu-id="6c46f-125">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![](~/media/pull-request-header.png)

<span data-ttu-id="6c46f-126">El uso de este proceso nos ayuda a usar la funcionalidad de GitHub para mejorar las contribuciones y para mantener un producto de alta calidad para la comunidad de programación de Quantum.</span><span class="sxs-lookup"><span data-stu-id="6c46f-126">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="6c46f-127">Cómo crear una solicitud de incorporación de cambios</span><span class="sxs-lookup"><span data-stu-id="6c46f-127">How to Make a Pull Request</span></span> ##

<span data-ttu-id="6c46f-128">Hay dos formas principales de hacer una solicitud de incorporación de cambios.</span><span class="sxs-lookup"><span data-stu-id="6c46f-128">There are two main ways to make a pull request.</span></span>
<span data-ttu-id="6c46f-129">En el caso de los cambios pequeños que solo afectan a un solo archivo, la interfaz Web de GitHub se puede usar para realizar una solicitud de incorporación de cambios completamente en línea.</span><span class="sxs-lookup"><span data-stu-id="6c46f-129">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span>
<span data-ttu-id="6c46f-130">En el caso de las contribuciones más complicadas, a menudo es más fácil usar el equipo local para preparar una solicitud de incorporación de cambios en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="6c46f-130">For more complicated contributions, it's most often easier to use your local computer to prepare for a pull request first.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="6c46f-131">pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6c46f-131">Next steps</span></span> ##

<span data-ttu-id="6c46f-132">Enhorabuena por usar git para ayudar a la comunidad Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="6c46f-132">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="6c46f-133">Para obtener más información sobre cómo contribuir con el código, continúe con la siguiente guía.</span><span class="sxs-lookup"><span data-stu-id="6c46f-133">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6c46f-134">Obtener información sobre cómo colaborar en el código</span><span class="sxs-lookup"><span data-stu-id="6c46f-134">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)