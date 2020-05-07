---
title: Aprenda a instalar Microsoft Quantum Development Kit (QDK)
description: Cómo instalar el kit de desarrollo de Microsoft Quantum en los entornos de C#, Python y Jupyter Notebook.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680189"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="18ef8-103">Instalación de Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="18ef8-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="18ef8-104">Aprenda a instalar Microsoft Quantum Development Kit (QDK), para que pueda dar sus primeros pasos en la programación cuántica.</span><span class="sxs-lookup"><span data-stu-id="18ef8-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="18ef8-105">Microsoft Quantum Development Kit consta de:</span><span class="sxs-lookup"><span data-stu-id="18ef8-105">The QDK consists of:</span></span>

- <span data-ttu-id="18ef8-106">El lenguaje de programación Q#</span><span class="sxs-lookup"><span data-stu-id="18ef8-106">the Q# programming language</span></span>
- <span data-ttu-id="18ef8-107">Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#</span><span class="sxs-lookup"><span data-stu-id="18ef8-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="18ef8-108">API de los lenguajes Python y .NET (C#, F# y VB.NET) para ejecutar programas cuánticos escritos en Q#</span><span class="sxs-lookup"><span data-stu-id="18ef8-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="18ef8-109">Herramientas para facilitar el desarrollo</span><span class="sxs-lookup"><span data-stu-id="18ef8-109">tools to facilitate your development</span></span>

<span data-ttu-id="18ef8-110">A menudo, los programas en Q# se emparejan con un programa host escrito en un lenguaje .NET (normalmente C#) o en Python,</span><span class="sxs-lookup"><span data-stu-id="18ef8-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="18ef8-111">lo que nos permite llamar a operaciones cuánticas desde dentro de un programa clásico.</span><span class="sxs-lookup"><span data-stu-id="18ef8-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="18ef8-112">Además, QDK proporciona compatibilidad de Q# con cuadernos de Jupyter Notebooks con el kernel IQ # de Jupyter.</span><span class="sxs-lookup"><span data-stu-id="18ef8-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="18ef8-113">QDK está disponible para varios entornos de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="18ef8-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="18ef8-114">Seleccione la configuración preferida en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="18ef8-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="18ef8-115">[Aplicación de línea de comandos de Q#:](xref:microsoft.quantum.install.standalone) elija este enfoque si desea trabajar con Q# desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="18ef8-115">[Q# command line application:](xref:microsoft.quantum.install.standalone) choose this approach if you want to work with Q# from the command line.</span></span> <span data-ttu-id="18ef8-116">No requiere un controlador ni un programa host como las opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="18ef8-116">This does not require a driver or a host program like the below options.</span></span>
- <span data-ttu-id="18ef8-117">[Instalación de Q# para cuadernos de Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) elija este entorno para ejecutar código Q# en celdas en las que se haya insertado texto o crear tutoriales interactivos de computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="18ef8-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 
- <span data-ttu-id="18ef8-118">[Desarrollo con Q# y Python:](xref:microsoft.quantum.install.python) si desea combinar Python y Q# para crear un programa host de Python que llame a operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="18ef8-118">[Develop with Q# and Python:](xref:microsoft.quantum.install.python) if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="18ef8-119">[Desarrollo con Q# y C# o F#:](xref:microsoft.quantum.install.cs) si desea combinar C# o F# con Q# para crear un programa host de .NET que llame a operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="18ef8-119">[Develop with Q# and C# or F#:](xref:microsoft.quantum.install.cs) if you want to combine C# or F# and Q# to create a .NET host program that calls Q# operations.</span></span>
