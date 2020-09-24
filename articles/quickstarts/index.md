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
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a>Configuración del kit de desarrollo de Microsoft Quantum (QDK)

Aprenda a configurar el kit de desarrollo de Microsoft Quantum (QDK) para que pueda dar sus primeros pasos en la programación cuántica. Microsoft Quantum Development Kit consta de:

- Lenguaje de programación Q#
- Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#.
- API de los lenguajes Python y .NET (C#, F# y VB.NET) para ejecutar programas cuánticos escritos en Q#.
- Herramientas que facilitan el desarrollo

Los programas de Q# se pueden ejecutar como aplicaciones independientes mediante Visual Studio Code o Visual Studio, mediante cuadernos de Jupyter Notebook con el kernel de IQ# para Jupyter, o con la ayuda de un programa host escrito en Python o en un lenguaje .NET (C#, F#). También puede ejecutar programas de Q# en línea mediante [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) o [Docker](#use-the-qdk-with-docker). 

## <a name="options-for-setting-up-the-qdk"></a>Opciones para configurar el QDK

Puede usar el QDK de tres maneras:

- [Instalación local del QDK](#install-the-qdk-locally)
- [Uso del QDK en línea](#use-the-qdk-online)
- [Uso de una imagen de Docker del QDK](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a>Instalación local del QDK

Puede desarrollar código de Q# en la mayoría de sus IDE favoritos, e integrar Q# con otros lenguajes, como Python y .NET (C# , F#).

|&nbsp; | **VS Code<br> (2019 o posterior)**| **Visual Studio 2019<br> o posterior** | **Jupyter Notebooks** | **Línea de comandos**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|**SO** |Windows, macOS, Linux |Solo Windows. |Windows, macOS, Linux |Windows, macOS, Linux |
|<br>**Q# independiente** |<br>[Instalación](xref:microsoft.quantum.install.standalone) |<br> [Instalación](xref:microsoft.quantum.install.standalone)  |<br> [Instalación](xref:microsoft.quantum.install.jupyter) |<br>[Instalación](xref:microsoft.quantum.install.standalone)|
|**Q#  y Python** |[Instalación](xref:microsoft.quantum.install.python) |[Instalación](xref:microsoft.quantum.install.python) |[Instalación](xref:microsoft.quantum.install.jupyter) |[Instalación](xref:microsoft.quantum.install.python) |
|**Q# y .NET (C#, F#)**|[Instalación](xref:microsoft.quantum.install.cs) |[Instalación](xref:microsoft.quantum.install.cs)|&#10006; |[Instalación](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a>Uso del QDK en línea

También puede desarrollar código de Q# sin necesidad de instalar nada localmente con estas opciones:

|Recurso|Ventajas|Limitaciones|
|---|---|---|
|[**Visual Studio Codespaces**](xref:microsoft.quantum.install.standalone)|Un entorno de desarrollo enriquecido en línea.  |Requiere una suscripción y un plan de Azure. |
|[**Binder**](xref:microsoft.quantum.install.binder) | Experiencia de cuaderno en línea gratuita. |Sin persistencia. |

## <a name="use-the-qdk-with-docker"></a>Uso del QDK con Docker

Puede usar nuestra imagen de Docker del QDK en su instalación de Docker local o en la nube mediante cualquier servicio que admita imágenes de Docker, como ACI.

Puede descargar la imagen de Docker de IQ# de https://github.com/microsoft/iqsharp/#using-iq-as-a-container. 

También puede usar Docker con un contenedor de desarrollo remoto de Visual Studio Code para definir rápidamente los entornos de desarrollo. Para más información sobre los contenedores de desarrollo de VS Code, consulte https://github.com/microsoft/Quantum/tree/master/.devcontainer.

## <a name="next-steps"></a>Pasos siguientes

Los flujos de trabajo de cada una de estas configuraciones se describen y comparan en [Maneras de ejecutar un programa de Q#](xref:microsoft.quantum.guide.host-programs).
