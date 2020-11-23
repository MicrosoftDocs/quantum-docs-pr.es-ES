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
ms.openlocfilehash: f0c3df1998f9b64ff6544867b83a7afe52b6f46d
ms.sourcegitcommit: fd57a845d013ae4578715d04b1ed1edc1c8ff6b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94870866"
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

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><b>Código de VS<br>(2019 o posterior)</b></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="VS Studio" width="50"/><br><b>VS Studio<br>(2019 o posterior)</b></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><b>Jupyter Notebooks</b></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><b>Línea de comandos</b></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><b>Sistemas operativos admitidos:</b></td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Solo Windows.</td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Windows, macOS, Linux</td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><b>Q# independiente</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Instalación</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Instalación</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">Instalación</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Instalación</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><b>Q# y Python</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalación</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalación</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">Instalación</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalación</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><b>Q# y .NET (C#, F#)</b></td> 
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Instalación</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Instalación</a></td>
        <td align="center">&#10006;</td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Instalación</a></td>
   </tr>
</table>

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
