---
title: Aprenda a instalar Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 0e9dd1c74316eeb1fa7bbbf657d2e78231ee4294
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036515"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="f02d2-102">Instalación de Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="f02d2-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="f02d2-103">Aprenda a instalar Microsoft Quantum Development Kit (QDK), para que pueda dar sus primeros pasos en la programación cuántica.</span><span class="sxs-lookup"><span data-stu-id="f02d2-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="f02d2-104">Microsoft Quantum Development Kit consta de:</span><span class="sxs-lookup"><span data-stu-id="f02d2-104">The QDK consists of:</span></span>

- <span data-ttu-id="f02d2-105">El lenguaje de programación Q#</span><span class="sxs-lookup"><span data-stu-id="f02d2-105">the Q# programming language</span></span>
- <span data-ttu-id="f02d2-106">Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#</span><span class="sxs-lookup"><span data-stu-id="f02d2-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="f02d2-107">API de los lenguajes Python y .NET (C#, F# y VB.NET) para ejecutar programas cuánticos escritos en Q#</span><span class="sxs-lookup"><span data-stu-id="f02d2-107">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="f02d2-108">Herramientas para facilitar el desarrollo</span><span class="sxs-lookup"><span data-stu-id="f02d2-108">tools to facilitate your development</span></span>

<span data-ttu-id="f02d2-109">A menudo, los programas en Q# se emparejan con un programa host escrito en un lenguaje .NET (normalmente C#) o en Python,</span><span class="sxs-lookup"><span data-stu-id="f02d2-109">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="f02d2-110">lo que nos permite llamar a operaciones cuánticas desde dentro de un programa clásico.</span><span class="sxs-lookup"><span data-stu-id="f02d2-110">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="f02d2-111">Además, QDK proporciona compatibilidad de Q# con cuadernos de Jupyter Notebooks con el kernel IQ # de Jupyter.</span><span class="sxs-lookup"><span data-stu-id="f02d2-111">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="f02d2-112">QDK está disponible para varios entornos de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="f02d2-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="f02d2-113">Seleccione la configuración preferida en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f02d2-113">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="f02d2-114">[Instalación de Q# para C#:](xref:microsoft.quantum.install.cs) elija este entorno si desea combinar C# y Q# para crear un programa host en C# que llame a operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="f02d2-114">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="f02d2-115">[Instalación de Q# para Python:](xref:microsoft.quantum.install.python) elija este entorno si desea combinar Python y Q# para crear un programa host en Python que llame a operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="f02d2-115">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="f02d2-116">[Instalación de Q# para cuadernos de Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) elija este entorno para ejecutar código Q# en celdas en las que se haya insertado texto o crear tutoriales interactivos de computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="f02d2-116">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="f02d2-117">No elija este entorno si desea combinar Q# con un programa host clásico externo.</span><span class="sxs-lookup"><span data-stu-id="f02d2-117">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
