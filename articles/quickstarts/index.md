---
title: Configuración del kit de desarrollo de Microsoft Quantum (QDK)
description: Aprenda a configurar el kit de desarrollo de Microsoft Quantum en distintos entornos.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: quickstart
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15067f1762f4468345beee38c98e1b943081fc1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859022"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="17e15-103">Configuración del kit de desarrollo de Microsoft Quantum (QDK)</span><span class="sxs-lookup"><span data-stu-id="17e15-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="17e15-104">Aprenda a configurar el kit de desarrollo de Microsoft Quantum (QDK) para que pueda dar sus primeros pasos en la programación cuántica.</span><span class="sxs-lookup"><span data-stu-id="17e15-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="17e15-105">Microsoft Quantum Development Kit consta de:</span><span class="sxs-lookup"><span data-stu-id="17e15-105">The QDK consists of:</span></span>

- <span data-ttu-id="17e15-106">Lenguaje de programación Q#</span><span class="sxs-lookup"><span data-stu-id="17e15-106">The Q# programming language</span></span>
- <span data-ttu-id="17e15-107">Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#.</span><span class="sxs-lookup"><span data-stu-id="17e15-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="17e15-108">API de los lenguajes Python y .NET (C#, F# y VB.NET) para ejecutar programas cuánticos escritos en Q#.</span><span class="sxs-lookup"><span data-stu-id="17e15-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="17e15-109">Herramientas que facilitan el desarrollo</span><span class="sxs-lookup"><span data-stu-id="17e15-109">Tools to facilitate your development</span></span>

<span data-ttu-id="17e15-110">Los programas de Q# se pueden ejecutar como aplicaciones independientes mediante Visual Studio Code o Visual Studio, mediante cuadernos de Jupyter Notebook con el kernel de IQ# para Jupyter, o con la ayuda de un programa host escrito en Python o en un lenguaje .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="17e15-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="17e15-111">También puede ejecutar programas de Q# en línea mediante [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) o [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="17e15-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="17e15-112">Opciones para configurar el QDK</span><span class="sxs-lookup"><span data-stu-id="17e15-112">Options for setting up the QDK</span></span>

<span data-ttu-id="17e15-113">Puede usar el QDK de tres maneras:</span><span class="sxs-lookup"><span data-stu-id="17e15-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="17e15-114">Instalación local del QDK</span><span class="sxs-lookup"><span data-stu-id="17e15-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="17e15-115">Uso del QDK en línea</span><span class="sxs-lookup"><span data-stu-id="17e15-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="17e15-116">Uso de una imagen de Docker del QDK</span><span class="sxs-lookup"><span data-stu-id="17e15-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="17e15-117">Instalación local del QDK</span><span class="sxs-lookup"><span data-stu-id="17e15-117">Install the QDK locally</span></span>

<span data-ttu-id="17e15-118">Puede desarrollar código de Q# en la mayoría de sus IDE favoritos, e integrar Q# con otros lenguajes, como Python y .NET (C# , F#).</span><span class="sxs-lookup"><span data-stu-id="17e15-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="17e15-119"><b>Código de VS</span><span class="sxs-lookup"><span data-stu-id="17e15-119"><b>VS Code</span></span><br><span data-ttu-id="17e15-120">(2019 o posterior)</b></span><span class="sxs-lookup"><span data-stu-id="17e15-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><span data-ttu-id="17e15-121"><b>Visual Studio</span><span class="sxs-lookup"><span data-stu-id="17e15-121"><b>Visual Studio</span></span><br><span data-ttu-id="17e15-122">(2019 o posterior)</b></span><span class="sxs-lookup"><span data-stu-id="17e15-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="17e15-123"><b>Jupyter Notebooks</b></span><span class="sxs-lookup"><span data-stu-id="17e15-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="17e15-124"><b>Línea de comandos</b></span><span class="sxs-lookup"><span data-stu-id="17e15-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="17e15-125"><b>Sistemas operativos admitidos:</b></span><span class="sxs-lookup"><span data-stu-id="17e15-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="17e15-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="17e15-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="17e15-127">Solo Windows.</span><span class="sxs-lookup"><span data-stu-id="17e15-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="17e15-128">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="17e15-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="17e15-129">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="17e15-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="17e15-130"><b>Q# independiente</b></span><span class="sxs-lookup"><span data-stu-id="17e15-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="17e15-131"><a href="xref:microsoft.quantum.install.standalone">Instalación</a></span><span class="sxs-lookup"><span data-stu-id="17e15-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="17e15-132"><a href="xref:microsoft.quantum.install.standalone">Instalación</a></span><span class="sxs-lookup"><span data-stu-id="17e15-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="17e15-133"><a href="xref:microsoft.quantum.install.jupyter">Instalación</a></span><span class="sxs-lookup"><span data-stu-id="17e15-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="17e15-134"><a href="xref:microsoft.quantum.install.standalone">Instalación</a></span><span class="sxs-lookup"><span data-stu-id="17e15-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="17e15-135"><b>Q# y Python</b></span><span class="sxs-lookup"><span data-stu-id="17e15-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="17e15-136"><a href="xref:microsoft.quantum.install.python">Instalación</a></span><span class="sxs-lookup"><span data-stu-id="17e15-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="17e15-137"><a href="xref:microsoft.quantum.install.python">Instalación</a></span><span class="sxs-lookup"><span data-stu-id="17e15-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="17e15-138"><a href="xref:microsoft.quantum.install.python">Instalación</a></span><span class="sxs-lookup"><span data-stu-id="17e15-138"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="17e15-139"><a href="xref:microsoft.quantum.install.python">Instalación</a></span><span class="sxs-lookup"><span data-stu-id="17e15-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="17e15-140"><b>Q# y .NET (C#, F#)</b></span><span class="sxs-lookup"><span data-stu-id="17e15-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="17e15-141"><a href="xref:microsoft.quantum.install.cs">Instalación</a></span><span class="sxs-lookup"><span data-stu-id="17e15-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="17e15-142"><a href="xref:microsoft.quantum.install.cs">Instalación</a></span><span class="sxs-lookup"><span data-stu-id="17e15-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="17e15-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="17e15-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="17e15-144"><a href="xref:microsoft.quantum.install.cs">Instalación</a></span><span class="sxs-lookup"><span data-stu-id="17e15-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="17e15-145">Uso del QDK en línea</span><span class="sxs-lookup"><span data-stu-id="17e15-145">Use the QDK Online</span></span>

<span data-ttu-id="17e15-146">También puede desarrollar código de Q# sin necesidad de instalar nada localmente con estas opciones:</span><span class="sxs-lookup"><span data-stu-id="17e15-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="17e15-147">Recurso</span><span class="sxs-lookup"><span data-stu-id="17e15-147">Resource</span></span>|<span data-ttu-id="17e15-148">Ventajas</span><span class="sxs-lookup"><span data-stu-id="17e15-148">Advantages</span></span>|<span data-ttu-id="17e15-149">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="17e15-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="17e15-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="17e15-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="17e15-151">Un entorno de desarrollo enriquecido en línea.</span><span class="sxs-lookup"><span data-stu-id="17e15-151">A rich online development environment</span></span>  |<span data-ttu-id="17e15-152">Requiere una suscripción y un plan de Azure.</span><span class="sxs-lookup"><span data-stu-id="17e15-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="17e15-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="17e15-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="17e15-154">Experiencia de cuaderno en línea gratuita.</span><span class="sxs-lookup"><span data-stu-id="17e15-154">Free online notebook experience</span></span> |<span data-ttu-id="17e15-155">Sin persistencia.</span><span class="sxs-lookup"><span data-stu-id="17e15-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="17e15-156">Uso del QDK con Docker</span><span class="sxs-lookup"><span data-stu-id="17e15-156">Use the QDK with Docker</span></span>

<span data-ttu-id="17e15-157">Puede usar nuestra imagen de Docker del QDK en su instalación de Docker local o en la nube mediante cualquier servicio que admita imágenes de Docker, como ACI.</span><span class="sxs-lookup"><span data-stu-id="17e15-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="17e15-158">Puede descargar la imagen de Docker de IQ# de https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="17e15-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="17e15-159">También puede usar Docker con un contenedor de desarrollo remoto de Visual Studio Code para definir rápidamente los entornos de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="17e15-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="17e15-160">Para más información sobre los contenedores de desarrollo de VS Code, consulte https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="17e15-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="17e15-161">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="17e15-161">Next steps</span></span>

<span data-ttu-id="17e15-162">Los flujos de trabajo de cada una de estas configuraciones se describen y comparan en [Maneras de ejecutar un programa de Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="17e15-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
