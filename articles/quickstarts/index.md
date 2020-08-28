---
title: Instalación de Microsoft Quantum Development Kit (QDK)
description: Aprenda a instalar Microsoft Quantum Development Kit en distintos entornos.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3aafe78d5910027e2836f7dce72c064e75fc4436
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863708"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="889c7-103">Instalación de Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="889c7-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="889c7-104">Aprenda a instalar Microsoft Quantum Development Kit (QDK), para que pueda dar sus primeros pasos en la programación cuántica.</span><span class="sxs-lookup"><span data-stu-id="889c7-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="889c7-105">Microsoft Quantum Development Kit consta de:</span><span class="sxs-lookup"><span data-stu-id="889c7-105">The QDK consists of:</span></span>

- <span data-ttu-id="889c7-106">Lenguaje de programación Q#</span><span class="sxs-lookup"><span data-stu-id="889c7-106">The Q# programming language</span></span>
- <span data-ttu-id="889c7-107">Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#.</span><span class="sxs-lookup"><span data-stu-id="889c7-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="889c7-108">API de los lenguajes Python y .NET (C#, F# y VB.NET) para ejecutar programas cuánticos escritos en Q#.</span><span class="sxs-lookup"><span data-stu-id="889c7-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="889c7-109">Herramientas que facilitan el desarrollo</span><span class="sxs-lookup"><span data-stu-id="889c7-109">Tools to facilitate your development</span></span>

<span data-ttu-id="889c7-110">Los programas de Q# se pueden ejecutar como aplicaciones independientes mediante Visual Studio Code o Visual Studio, o bien mediante cuadernos de Jupyter Notebook con el kernel de IQ# para Jupyter.</span><span class="sxs-lookup"><span data-stu-id="889c7-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>
<span data-ttu-id="889c7-111">También se pueden emparejar con un programa host escrito en un lenguaje .NET (normalmente C#) o Python, lo que permite llamar a operaciones cuánticas desde dentro de un programa clásico.</span><span class="sxs-lookup"><span data-stu-id="889c7-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="889c7-112">Los flujos de trabajo de cada una de estas configuraciones se describen y comparan en [Maneras de ejecutar un programa de Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="889c7-112">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

<span data-ttu-id="889c7-113">Para continuar con la instalación del QDK y la creación de proyectos de Q#, seleccione la configuración que prefiera:</span><span class="sxs-lookup"><span data-stu-id="889c7-113">To proceed with installing the QDK and creating Q# projects, select your preferred setup:</span></span>

<span data-ttu-id="889c7-114">[Desarrollar con aplicaciones de Q#](xref:microsoft.quantum.install.standalone): elija este método si desea trabajar con Q# desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="889c7-114">[Develop with Q# applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command prompt.</span></span> <span data-ttu-id="889c7-115">No requiere un controlador ni un programa host como las opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="889c7-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="889c7-116">[Desarrollo con cuadernos en Q# de Jupyter Notebook](xref:microsoft.quantum.install.jupyter): elija este entorno para ejecutar código de Q# en celdas con texto insertado o para crear tutoriales interactivos de computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="889c7-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="889c7-117">[Desarrollo con Q# y Python](xref:microsoft.quantum.install.python): permite combinar Python y Q# para crear un programa host de Python que llame a operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="889c7-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="889c7-118">[Desarrollo con Q# y .NET](xref:microsoft.quantum.install.cs): si desea combinar C#, F# o VB.NET con Q# para crear un programa host de .NET que llame a operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="889c7-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
