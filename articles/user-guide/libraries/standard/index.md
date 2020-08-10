---
title: Introducción a las bibliotecas estándar de Microsoft Q#
description: Obtenga información sobre las bibliotecas estándar de Microsoft Q# que definen las operaciones, las funciones y los tipos de datos que se usan en los programas cuánticos.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4db227fcf159331f9f8456c474ce6d64111c21df
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868481"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Introducción a las bibliotecas estándar de Q#

Q# es compatible con las diferentes operaciones, funciones y tipos definidos por el usuario que componen las *bibliotecas estándar* de Q#.
Los [paquetes NuGet de `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) que se instalan durante la [instalación y validación](xref:microsoft.quantum.install) proporcionan el compilador de Q# y las partes de la biblioteca estándar que implementan las máquinas de destino.
El [paquete de `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) proporciona la parte de las bibliotecas estándar de Q# que son portátiles entre las máquinas de destino.

Los símbolos definidos por las bibliotecas estándar de Q# se definen con más detalle en la [documentación de la API](xref:microsoft.quantum.standardlibsintro).

En las secciones siguientes, describiremos las características más destacables de cada parte de la biblioteca estándar y proporcionaremos algún contexto sobre cómo usar cada característica en la práctica.
