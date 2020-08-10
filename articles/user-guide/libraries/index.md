---
title: Bibliotecas del kit de desarrollo de Microsoft Quantum
description: Información general de las bibliotecas estándar, química y de valores numéricos incluidas en el kit de desarrollo de Microsoft Quantum.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: d61fe459362fdb5f3550768a26b34656a8a538a7
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869110"
---
# <a name="overview-of-no-locq-libraries"></a><span data-ttu-id="b0457-103">Introducción a las bibliotecas de Q#</span><span class="sxs-lookup"><span data-stu-id="b0457-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="b0457-104">El kit de desarrollo de Microsoft Quantum incluye varias bibliotecas para facilitar el desarrollo de aplicaciones cuánticas en Q#.</span><span class="sxs-lookup"><span data-stu-id="b0457-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="b0457-105">En esta sección de la documentación, se describen estas bibliotecas y cómo usarlas en los programas.</span><span class="sxs-lookup"><span data-stu-id="b0457-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="b0457-106">[**Bibliotecas estándar**](xref:microsoft.quantum.libraries.standard.intro): En esta sección se describen el preludio, que define la interfaz entre los programas de Q# y las máquinas de destino, y el canon, una biblioteca de Q# que proporciona operaciones y funciones de uso general para escribir programas de Q#.</span><span class="sxs-lookup"><span data-stu-id="b0457-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="b0457-107">[**Biblioteca de química cuántica**](xref:microsoft.quantum.chemistry.concepts.intro): En esta sección se describe la biblioteca de química cuántica, que proporciona un modelo de datos para cargar representaciones de funciones de Hamilton fermiónicas y funciones y operaciones de simulación cuántica que actúan en estas representaciones.</span><span class="sxs-lookup"><span data-stu-id="b0457-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="b0457-108">[**Biblioteca de valores numéricos cuánticos**](xref:microsoft.quantum.numerics.intro): En esta sección se describe la biblioteca de valores numéricos cuánticos, que proporciona implementaciones para un host de funciones matemáticas.</span><span class="sxs-lookup"><span data-stu-id="b0457-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="b0457-109">Admite representaciones de enteros (con y sin signo) y de punto fijo.</span><span class="sxs-lookup"><span data-stu-id="b0457-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>
- <span data-ttu-id="b0457-110">[**Biblioteca de aprendizaje automático cuántico**](xref:microsoft.quantum.machine-learning.concepts.intro) En esta sección se describe la biblioteca de aprendizaje automático cuántico, que proporciona una implementación de los clasificadores secuenciales que aprovechan las ventajas de la computación cuántica para comprender los datos.</span><span class="sxs-lookup"><span data-stu-id="b0457-110">[**Quantum machine learning library**](xref:microsoft.quantum.machine-learning.concepts.intro): This section describes the quantum machine learning library, which provides an implementation of the sequential classifiers that take advantage of quantum computing to understand data.</span></span>

<span data-ttu-id="b0457-111">Los orígenes de las bibliotecas y los ejemplos de código se pueden obtener de GitHub.</span><span class="sxs-lookup"><span data-stu-id="b0457-111">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span>
<span data-ttu-id="b0457-112">Para más información, consulte [Licencias](xref:microsoft.quantum.libraries.licensing).</span><span class="sxs-lookup"><span data-stu-id="b0457-112">See [Licensing](xref:microsoft.quantum.libraries.licensing) for further information.</span></span> <span data-ttu-id="b0457-113">Tenga en cuenta que también hay disponibles referencias de paquete ("archivos binarios") para las bibliotecas y ofrecen otra manera de incluir las bibliotecas en los proyectos.</span><span class="sxs-lookup"><span data-stu-id="b0457-113">Note that package references ("binaries") are available also for the libraries and offer another way of including the libraries in projects.</span></span>
<span data-ttu-id="b0457-114">Se pueden obtener fácilmente en [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="b0457-114">A convenient way of obtaining them is via [NuGet](https://nuget.org).</span></span>
