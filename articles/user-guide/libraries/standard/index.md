---
title: Introducción a las bibliotecas estándar de Microsoft Q#
description: Obtenga información sobre las bibliotecas estándar de Microsoft Q# que definen las operaciones, las funciones y los tipos de datos que se usan en los programas cuánticos.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 63709015a12a7f972a676018970143ca163e92d0
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836019"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a><span data-ttu-id="6db98-103">Introducción a las bibliotecas estándar de Q#</span><span class="sxs-lookup"><span data-stu-id="6db98-103">Introduction to the Q# Standard Libraries</span></span>

<span data-ttu-id="6db98-104">Q# es compatible con las diferentes operaciones, funciones y tipos definidos por el usuario que componen las *bibliotecas estándar* de Q#.</span><span class="sxs-lookup"><span data-stu-id="6db98-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="6db98-105">Los [paquetes NuGet de `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) que se instalan durante la [instalación y validación](xref:microsoft.quantum.install) proporcionan el compilador de Q# y las partes de la biblioteca estándar que implementan las máquinas de destino.</span><span class="sxs-lookup"><span data-stu-id="6db98-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="6db98-106">El [paquete de `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) proporciona la parte de las bibliotecas estándar de Q# que son portátiles entre las máquinas de destino.</span><span class="sxs-lookup"><span data-stu-id="6db98-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="6db98-107">Los símbolos definidos por las bibliotecas estándar de Q# se definen con más detalle en la [documentación de la API](xref:microsoft.quantum.apiref-intro).</span><span class="sxs-lookup"><span data-stu-id="6db98-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.apiref-intro).</span></span>

<span data-ttu-id="6db98-108">En las secciones siguientes, describiremos las características más destacables de cada parte de la biblioteca estándar y proporcionaremos algún contexto sobre cómo usar cada característica en la práctica.</span><span class="sxs-lookup"><span data-stu-id="6db98-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
