---
title: Introducción a las bibliotecas estándar de Microsoft Q#
description: Obtenga información sobre las bibliotecas estándar de Microsoft Q# que definen las operaciones, las funciones y los tipos de datos que se usan en los programas cuánticos.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 820ad885e7134aa723116d4c9f853d88210a5514
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907161"
---
# <a name="introduction-to-the-q-standard-libraries"></a>Introducción a las bibliotecas estándar de Q# #

Q# es compatible con una variedad de diferentes operaciones, funciones y tipos definidos por el usuario útiles que componen las *bibliotecas estándar* de Q#.
Los [paquetes NuGet de `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) que se instalan durante la [instalación y validación](xref:microsoft.quantum.install) proporcionan el compilador de Q# y las partes de la biblioteca estándar que implementan las máquinas de destino.
El [paquete de `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) proporciona la parte de las bibliotecas estándar de Q# que son portátiles entre las máquinas de destino.

Los símbolos definidos por las bibliotecas estándar de Q# se definen con más detalle en la [documentación de la API](xref:microsoft.quantum.standardlibsintro).

En las secciones siguientes, describiremos las características más destacables de cada parte de la biblioteca estándar y proporcionaremos algún contexto sobre cómo usar cada característica en la práctica.
