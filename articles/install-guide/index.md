---
title: Aprenda a instalar Microsoft Quantum Development Kit (QDK)
description: Cómo instalar el kit de desarrollo de Microsoft Quantum en los entornos de C#, Python y Jupyter Notebook.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 5fafb736f34d27f9233370a0a8a66c0613606048
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "77904781"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="46ac9-103">Instalación de Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="46ac9-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="46ac9-104">Aprenda a instalar Microsoft Quantum Development Kit (QDK), para que pueda dar sus primeros pasos en la programación cuántica.</span><span class="sxs-lookup"><span data-stu-id="46ac9-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="46ac9-105">Microsoft Quantum Development Kit consta de:</span><span class="sxs-lookup"><span data-stu-id="46ac9-105">The QDK consists of:</span></span>

- <span data-ttu-id="46ac9-106">El lenguaje de programación Q#</span><span class="sxs-lookup"><span data-stu-id="46ac9-106">the Q# programming language</span></span>
- <span data-ttu-id="46ac9-107">Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#</span><span class="sxs-lookup"><span data-stu-id="46ac9-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="46ac9-108">API de los lenguajes Python y .NET (C#, F# y VB.NET) para ejecutar programas cuánticos escritos en Q#</span><span class="sxs-lookup"><span data-stu-id="46ac9-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="46ac9-109">Herramientas para facilitar el desarrollo</span><span class="sxs-lookup"><span data-stu-id="46ac9-109">tools to facilitate your development</span></span>

<span data-ttu-id="46ac9-110">A menudo, los programas en Q# se emparejan con un programa host escrito en un lenguaje .NET (normalmente C#) o en Python,</span><span class="sxs-lookup"><span data-stu-id="46ac9-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="46ac9-111">lo que nos permite llamar a operaciones cuánticas desde dentro de un programa clásico.</span><span class="sxs-lookup"><span data-stu-id="46ac9-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="46ac9-112">Además, QDK proporciona compatibilidad de Q# con cuadernos de Jupyter Notebooks con el kernel IQ # de Jupyter.</span><span class="sxs-lookup"><span data-stu-id="46ac9-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="46ac9-113">QDK está disponible para varios entornos de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="46ac9-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="46ac9-114">Seleccione la configuración preferida en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="46ac9-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="46ac9-115">[Instalación de Q# para C#:](xref:microsoft.quantum.install.cs) elija este entorno si desea combinar C# y Q# para crear un programa host en C# que llame a operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="46ac9-115">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="46ac9-116">[Instalación de Q# para Python:](xref:microsoft.quantum.install.python) elija este entorno si desea combinar Python y Q# para crear un programa host en Python que llame a operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="46ac9-116">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="46ac9-117">[Instalación de Q# para cuadernos de Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) elija este entorno para ejecutar código Q# en celdas en las que se haya insertado texto o crear tutoriales interactivos de computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="46ac9-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="46ac9-118">No elija este entorno si desea combinar Q# con un programa host clásico externo.</span><span class="sxs-lookup"><span data-stu-id="46ac9-118">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
