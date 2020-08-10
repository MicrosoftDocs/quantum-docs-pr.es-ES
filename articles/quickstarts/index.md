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
ms.openlocfilehash: 378970dc911ea5a794590f8336ffc6d3f9673285
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867580"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalación de Microsoft Quantum Development Kit (QDK)

Aprenda a instalar Microsoft Quantum Development Kit (QDK), para que pueda dar sus primeros pasos en la programación cuántica. Microsoft Quantum Development Kit consta de:

- Lenguaje de programación Q#
- Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#.
- API de los lenguajes Python y .NET (C#, F# y VB.NET) para ejecutar programas cuánticos escritos en Q#.
- Herramientas que facilitan el desarrollo

Los programas de Q# se pueden ejecutar como aplicaciones independientes mediante Visual Studio Code o Visual Studio, o bien mediante cuadernos de Jupyter Notebook con el kernel de IQ# para Jupyter.
También se pueden emparejar con un programa host escrito en un lenguaje .NET (normalmente C#) o Python, lo que permite llamar a operaciones cuánticas desde dentro de un programa clásico.

Los flujos de trabajo de cada una de estas configuraciones se describen y comparan en [Maneras de ejecutar un programa de Q#](xref:microsoft.quantum.guide.host-programs).

Para continuar con la instalación del QDK y la creación de proyectos de Q#, seleccione la configuración que prefiera:

[Desarrollo con aplicaciones de línea de comandos de Q#](xref:microsoft.quantum.install.standalone): elija este enfoque si desea trabajar con Q# desde la línea de comandos. No requiere un controlador ni un programa host como las opciones siguientes.

[Desarrollo con cuadernos en Q# de Jupyter Notebook](xref:microsoft.quantum.install.jupyter): elija este entorno para ejecutar código de Q# en celdas con texto insertado o para crear tutoriales interactivos de computación cuántica. 

[Desarrollo con Q# y Python](xref:microsoft.quantum.install.python): permite combinar Python y Q# para crear un programa host de Python que llame a operaciones de Q#.

[Desarrollo con Q# y .NET](xref:microsoft.quantum.install.cs): si desea combinar C#, F# o VB.NET con Q# para crear un programa host de .NET que llame a operaciones de Q#.
