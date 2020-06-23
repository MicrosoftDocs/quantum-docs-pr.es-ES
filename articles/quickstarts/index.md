---
title: Instalación de Microsoft Quantum Development Kit (QDK)
description: Aprenda a instalar Microsoft Quantum Development Kit en distintos entornos.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 6a52eb0a9cdf699e8bb37578ffa3d73fe96a990e
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273752"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="a2ddb-103">Instalación de Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="a2ddb-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="a2ddb-104">Aprenda a instalar Microsoft Quantum Development Kit (QDK), para que pueda dar sus primeros pasos en la programación cuántica.</span><span class="sxs-lookup"><span data-stu-id="a2ddb-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="a2ddb-105">Microsoft Quantum Development Kit consta de:</span><span class="sxs-lookup"><span data-stu-id="a2ddb-105">The QDK consists of:</span></span>

- <span data-ttu-id="a2ddb-106">El lenguaje de programación Q#</span><span class="sxs-lookup"><span data-stu-id="a2ddb-106">The Q# programming language</span></span>
- <span data-ttu-id="a2ddb-107">Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#</span><span class="sxs-lookup"><span data-stu-id="a2ddb-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="a2ddb-108">API de los lenguajes Python y .NET (C#, F# y VB.NET) para ejecutar programas cuánticos escritos en Q#</span><span class="sxs-lookup"><span data-stu-id="a2ddb-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="a2ddb-109">Herramientas que facilitan el desarrollo</span><span class="sxs-lookup"><span data-stu-id="a2ddb-109">Tools to facilitate your development</span></span>

<span data-ttu-id="a2ddb-110">Los programas de Q# se pueden ejecutar como aplicaciones independientes mediante Visual Studio Code o Visual Studio, o bien a través de cuadernos de Jupyter Notebook con el kernel de IQ# Jupyter.</span><span class="sxs-lookup"><span data-stu-id="a2ddb-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="a2ddb-111">También se pueden emparejar con un programa host escrito en un lenguaje .NET (normalmente C#) o Python, lo que permite llamar a operaciones cuánticas desde dentro de un programa clásico.</span><span class="sxs-lookup"><span data-stu-id="a2ddb-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="a2ddb-112">QDK está disponible para varios entornos de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="a2ddb-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="a2ddb-113">Seleccione la configuración que prefiera entre:</span><span class="sxs-lookup"><span data-stu-id="a2ddb-113">Select your preferred setup from:</span></span>

<span data-ttu-id="a2ddb-114">[Desarrollo con aplicaciones de línea de comandos de Q#](xref:microsoft.quantum.install.standalone): elija este enfoque si desea trabajar con Q# desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="a2ddb-114">[Develop with Q# command line applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command line.</span></span> <span data-ttu-id="a2ddb-115">No requiere un controlador ni un programa host como las opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="a2ddb-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="a2ddb-116">[Desarrollo con cuadernos de Jupyter Notebook de Q#](xref:microsoft.quantum.install.jupyter): elija este entorno para ejecutar código Q# en celdas en las que se haya insertado texto o para crear tutoriales interactivos de computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="a2ddb-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="a2ddb-117">[Desarrollo con Q# y Python](xref:microsoft.quantum.install.python): permite combinar Python y Q# para crear un programa host de Python que llame a operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="a2ddb-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="a2ddb-118">[Desarrollo con Q# y .NET](xref:microsoft.quantum.install.cs): si desea combinar C#, F# o VB.NET con Q# para crear un programa host de .NET que llame a operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="a2ddb-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
