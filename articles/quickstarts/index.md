---
title: Configuración del kit de desarrollo de Microsoft Quantum (QDK)
description: Aprenda a configurar el kit de desarrollo de Microsoft Quantum en distintos entornos.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834489"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="ba578-103">Configuración del kit de desarrollo de Microsoft Quantum (QDK)</span><span class="sxs-lookup"><span data-stu-id="ba578-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="ba578-104">Aprenda a configurar el kit de desarrollo de Microsoft Quantum (QDK) para que pueda dar sus primeros pasos en la programación cuántica.</span><span class="sxs-lookup"><span data-stu-id="ba578-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="ba578-105">Microsoft Quantum Development Kit consta de:</span><span class="sxs-lookup"><span data-stu-id="ba578-105">The QDK consists of:</span></span>

- <span data-ttu-id="ba578-106">Lenguaje de programación Q#</span><span class="sxs-lookup"><span data-stu-id="ba578-106">The Q# programming language</span></span>
- <span data-ttu-id="ba578-107">Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#.</span><span class="sxs-lookup"><span data-stu-id="ba578-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="ba578-108">API de los lenguajes Python y .NET (C#, F# y VB.NET) para ejecutar programas cuánticos escritos en Q#.</span><span class="sxs-lookup"><span data-stu-id="ba578-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="ba578-109">Herramientas que facilitan el desarrollo</span><span class="sxs-lookup"><span data-stu-id="ba578-109">Tools to facilitate your development</span></span>

<span data-ttu-id="ba578-110">Los programas de Q# se pueden ejecutar como aplicaciones independientes mediante Visual Studio Code o Visual Studio, mediante cuadernos de Jupyter Notebook con el kernel de IQ# para Jupyter, o con la ayuda de un programa host escrito en Python o en un lenguaje .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="ba578-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="ba578-111">También puede ejecutar programas de Q# en línea mediante [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) o [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="ba578-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="ba578-112">Opciones para configurar el QDK</span><span class="sxs-lookup"><span data-stu-id="ba578-112">Options for setting up the QDK</span></span>

<span data-ttu-id="ba578-113">Puede usar el QDK de tres maneras:</span><span class="sxs-lookup"><span data-stu-id="ba578-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="ba578-114">Instalación local del QDK</span><span class="sxs-lookup"><span data-stu-id="ba578-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="ba578-115">Uso del QDK en línea</span><span class="sxs-lookup"><span data-stu-id="ba578-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="ba578-116">Uso de una imagen de Docker del QDK</span><span class="sxs-lookup"><span data-stu-id="ba578-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="ba578-117">Instalación local del QDK</span><span class="sxs-lookup"><span data-stu-id="ba578-117">Install the QDK locally</span></span>

<span data-ttu-id="ba578-118">Puede desarrollar código de Q# en la mayoría de sus IDE favoritos, e integrar Q# con otros lenguajes, como Python y .NET (C# , F#).</span><span class="sxs-lookup"><span data-stu-id="ba578-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

|&nbsp; | <span data-ttu-id="ba578-119">**VS Code<br> (2019 o posterior)**</span><span class="sxs-lookup"><span data-stu-id="ba578-119">**VS Code<br>(2019 or later)**</span></span>| <span data-ttu-id="ba578-120">**Visual Studio 2019<br> o posterior**</span><span class="sxs-lookup"><span data-stu-id="ba578-120">**Visual Studio<br>(2019 or later)**</span></span> | <span data-ttu-id="ba578-121">**Jupyter Notebooks**</span><span class="sxs-lookup"><span data-stu-id="ba578-121">**Jupyter Notebooks**</span></span> | <span data-ttu-id="ba578-122">**Línea de comandos**</span><span class="sxs-lookup"><span data-stu-id="ba578-122">**Command line**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="ba578-123">**SO**</span><span class="sxs-lookup"><span data-stu-id="ba578-123">**OS**</span></span> |<span data-ttu-id="ba578-124">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="ba578-124">Windows, macOS, Linux</span></span> |<span data-ttu-id="ba578-125">Solo Windows.</span><span class="sxs-lookup"><span data-stu-id="ba578-125">Windows only</span></span> |<span data-ttu-id="ba578-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="ba578-126">Windows, macOS, Linux</span></span> |<span data-ttu-id="ba578-127">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="ba578-127">Windows, macOS, Linux</span></span> |
|<br><span data-ttu-id="ba578-128">**Q# independiente**</span><span class="sxs-lookup"><span data-stu-id="ba578-128">**Q# standalone**</span></span> |<br>[<span data-ttu-id="ba578-129">Instalación</span><span class="sxs-lookup"><span data-stu-id="ba578-129">Install</span></span>](xref:microsoft.quantum.install.standalone) |<br> [<span data-ttu-id="ba578-130">Instalación</span><span class="sxs-lookup"><span data-stu-id="ba578-130">Install</span></span>](xref:microsoft.quantum.install.standalone)  |<br> [<span data-ttu-id="ba578-131">Instalación</span><span class="sxs-lookup"><span data-stu-id="ba578-131">Install</span></span>](xref:microsoft.quantum.install.jupyter) |<br>[<span data-ttu-id="ba578-132">Instalación</span><span class="sxs-lookup"><span data-stu-id="ba578-132">Install</span></span>](xref:microsoft.quantum.install.standalone)|
|<span data-ttu-id="ba578-133">**Q#  y Python**</span><span class="sxs-lookup"><span data-stu-id="ba578-133">**Q#  and Python**</span></span> |[<span data-ttu-id="ba578-134">Instalación</span><span class="sxs-lookup"><span data-stu-id="ba578-134">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="ba578-135">Instalación</span><span class="sxs-lookup"><span data-stu-id="ba578-135">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="ba578-136">Instalación</span><span class="sxs-lookup"><span data-stu-id="ba578-136">Install</span></span>](xref:microsoft.quantum.install.jupyter) |[<span data-ttu-id="ba578-137">Instalación</span><span class="sxs-lookup"><span data-stu-id="ba578-137">Install</span></span>](xref:microsoft.quantum.install.python) |
|<span data-ttu-id="ba578-138">**Q# y .NET (C#, F#)**</span><span class="sxs-lookup"><span data-stu-id="ba578-138">**Q# and .NET (C#, F#)**</span></span>|[<span data-ttu-id="ba578-139">Instalación</span><span class="sxs-lookup"><span data-stu-id="ba578-139">Install</span></span>](xref:microsoft.quantum.install.cs) |[<span data-ttu-id="ba578-140">Instalación</span><span class="sxs-lookup"><span data-stu-id="ba578-140">Install</span></span>](xref:microsoft.quantum.install.cs)|<span data-ttu-id="ba578-141">&#10006;</span><span class="sxs-lookup"><span data-stu-id="ba578-141">&#10006;</span></span> |[<span data-ttu-id="ba578-142">Instalación</span><span class="sxs-lookup"><span data-stu-id="ba578-142">Install</span></span>](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a><span data-ttu-id="ba578-143">Uso del QDK en línea</span><span class="sxs-lookup"><span data-stu-id="ba578-143">Use the QDK Online</span></span>

<span data-ttu-id="ba578-144">También puede desarrollar código de Q# sin necesidad de instalar nada localmente con estas opciones:</span><span class="sxs-lookup"><span data-stu-id="ba578-144">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="ba578-145">Recurso</span><span class="sxs-lookup"><span data-stu-id="ba578-145">Resource</span></span>|<span data-ttu-id="ba578-146">Ventajas</span><span class="sxs-lookup"><span data-stu-id="ba578-146">Advantages</span></span>|<span data-ttu-id="ba578-147">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="ba578-147">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="ba578-148">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="ba578-148">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="ba578-149">Un entorno de desarrollo enriquecido en línea.</span><span class="sxs-lookup"><span data-stu-id="ba578-149">A rich online development environment</span></span>  |<span data-ttu-id="ba578-150">Requiere una suscripción y un plan de Azure.</span><span class="sxs-lookup"><span data-stu-id="ba578-150">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="ba578-151">**Binder**</span><span class="sxs-lookup"><span data-stu-id="ba578-151">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="ba578-152">Experiencia de cuaderno en línea gratuita.</span><span class="sxs-lookup"><span data-stu-id="ba578-152">Free online notebook experience</span></span> |<span data-ttu-id="ba578-153">Sin persistencia.</span><span class="sxs-lookup"><span data-stu-id="ba578-153">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="ba578-154">Uso del QDK con Docker</span><span class="sxs-lookup"><span data-stu-id="ba578-154">Use the QDK with Docker</span></span>

<span data-ttu-id="ba578-155">Puede usar nuestra imagen de Docker del QDK en su instalación de Docker local o en la nube mediante cualquier servicio que admita imágenes de Docker, como ACI.</span><span class="sxs-lookup"><span data-stu-id="ba578-155">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="ba578-156">Puede descargar la imagen de Docker de IQ# de https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="ba578-156">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="ba578-157">También puede usar Docker con un contenedor de desarrollo remoto de Visual Studio Code para definir rápidamente los entornos de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="ba578-157">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="ba578-158">Para más información sobre los contenedores de desarrollo de VS Code, consulte https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="ba578-158">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ba578-159">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ba578-159">Next steps</span></span>

<span data-ttu-id="ba578-160">Los flujos de trabajo de cada una de estas configuraciones se describen y comparan en [Maneras de ejecutar un programa de Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="ba578-160">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
