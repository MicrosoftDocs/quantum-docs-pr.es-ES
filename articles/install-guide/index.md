---
title: Instalación de Microsoft Quantum Development Kit (QDK)
description: Aprenda a instalar Microsoft Quantum Development Kit en distintos entornos.
author: natke
ms.author: nakersha
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: a5230f506bce02c331d22d6a428b3bd92052bbd4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327581"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalación de Microsoft Quantum Development Kit (QDK)

Aprenda a instalar Microsoft Quantum Development Kit (QDK), para que pueda dar sus primeros pasos en la programación cuántica. Microsoft Quantum Development Kit consta de:

- El lenguaje de programación Q#
- Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#
- API de los lenguajes Python y .NET (C#, F# y VB.NET) para ejecutar programas cuánticos escritos en Q#
- Herramientas que facilitan el desarrollo

Los programas de Q# se pueden ejecutar como aplicaciones independientes mediante Visual Studio Code o Visual Studio, o bien a través de cuadernos de Jupyter Notebook con el kernel de IQ# Jupyter.

También se pueden emparejar con un programa host escrito en un lenguaje .NET (normalmente C#) o Python, lo que permite llamar a operaciones cuánticas desde dentro de un programa clásico.

QDK está disponible para varios entornos de desarrollo. Seleccione la configuración que prefiera entre:

[Desarrollo con aplicaciones de línea de comandos de Q#](xref:microsoft.quantum.install.standalone): elija este enfoque si desea trabajar con Q# desde la línea de comandos. No requiere un controlador ni un programa host como las opciones siguientes.

[Desarrollo con cuadernos de Jupyter Notebook de Q#](xref:microsoft.quantum.install.jupyter): elija este entorno para ejecutar código Q# en celdas en las que se haya insertado texto o para crear tutoriales interactivos de computación cuántica. 

[Desarrollo con Q# y Python](xref:microsoft.quantum.install.python): permite combinar Python y Q# para crear un programa host de Python que llame a operaciones de Q#.

[Desarrollo con Q# y .NET](xref:microsoft.quantum.install.cs): si desea combinar C#, F# o VB.NET con Q# para crear un programa host de .NET que llame a operaciones de Q#.
