---
title: Uso de Q# bibliotecas adicionales
description: Obtenga información sobre cómo agregar Q# bibliotecas adicionales a las aplicaciones Quantum.
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: ef88ca765a394a7092eb0a60bf6f3615c082ef6a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869586"
---
# <a name="using-additional-no-locq-libraries"></a><span data-ttu-id="91c73-103">Uso de Q# bibliotecas adicionales</span><span class="sxs-lookup"><span data-stu-id="91c73-103">Using Additional Q# Libraries</span></span>

<span data-ttu-id="91c73-104">El kit de desarrollo de Quantum proporciona una funcionalidad adicional específica del dominio a través de _paquetes NuGet_ que se pueden agregar a los Q# proyectos.</span><span class="sxs-lookup"><span data-stu-id="91c73-104">The Quantum Development Kit provides additional domain-specific functionality through _NuGet packages_ that can be added to your Q# projects.</span></span>

| <span data-ttu-id="91c73-105">Q#Biblioteca</span><span class="sxs-lookup"><span data-stu-id="91c73-105">Q# Library</span></span>  | <span data-ttu-id="91c73-106">Detección de</span><span class="sxs-lookup"><span data-stu-id="91c73-106">NuGet package</span></span> | <span data-ttu-id="91c73-107">Notas</span><span class="sxs-lookup"><span data-stu-id="91c73-107">Notes</span></span> |
|---------|---------|--------|
| [<span data-ttu-id="91c73-108">Q#biblioteca estándar</span><span class="sxs-lookup"><span data-stu-id="91c73-108">Q# standard library</span></span>](xref:microsoft.quantum.libraries.standard.intro) | [<span data-ttu-id="91c73-109">**Microsoft. Quantum. Standard**</span><span class="sxs-lookup"><span data-stu-id="91c73-109">**Microsoft.Quantum.Standard**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | <span data-ttu-id="91c73-110">Se incluye de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="91c73-110">Included by default</span></span> |
| [<span data-ttu-id="91c73-111">Biblioteca de química cuántica</span><span class="sxs-lookup"><span data-stu-id="91c73-111">Quantum chemistry library</span></span>](xref:microsoft.quantum.chemistry.concepts.intro) | [<span data-ttu-id="91c73-112">**Microsoft.Quantum.Chemistry**</span><span class="sxs-lookup"><span data-stu-id="91c73-112">**Microsoft.Quantum.Chemistry**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [<span data-ttu-id="91c73-113">Biblioteca de valores numéricos cuánticos</span><span class="sxs-lookup"><span data-stu-id="91c73-113">Quantum numerics library</span></span>](xref:microsoft.quantum.numerics.intro) | [<span data-ttu-id="91c73-114">**Microsoft. Quantum. Numerics**</span><span class="sxs-lookup"><span data-stu-id="91c73-114">**Microsoft.Quantum.Numerics**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [<span data-ttu-id="91c73-115">Biblioteca de aprendizaje automático cuántico</span><span class="sxs-lookup"><span data-stu-id="91c73-115">Quantum machine learning library</span></span>](xref:microsoft.quantum.libraries.machine-learning.intro) | [<span data-ttu-id="91c73-116">**Microsoft.Quantum.MachineLearning**</span><span class="sxs-lookup"><span data-stu-id="91c73-116">**Microsoft.Quantum.MachineLearning**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

<span data-ttu-id="91c73-117">Una vez que haya instalado el kit de desarrollo de Quantum para usarlo con el entorno y el lenguaje de host preferidos, puede agregar fácilmente bibliotecas a Q# proyectos individuales sin necesidad de realizar ninguna instalación adicional.</span><span class="sxs-lookup"><span data-stu-id="91c73-117">Once you have installed the Quantum Development Kit for use with your preferred environment and host language, you can easily add libraries to individual Q# projects without any further installation.</span></span>

> [!NOTE]
> <span data-ttu-id="91c73-118">Algunas Q# bibliotecas pueden funcionar bien con herramientas adicionales que funcionan con sus Q# programas o que se integran con las aplicaciones host.</span><span class="sxs-lookup"><span data-stu-id="91c73-118">Some Q# libraries may work well with additional tools that work alongside your Q# programs, or that integrate with your host applications.</span></span>
> <span data-ttu-id="91c73-119">Por ejemplo, las [instrucciones de instalación](xref:microsoft.quantum.chemistry.concepts.installation) de la biblioteca de química describen cómo usar el [paquete **Microsoft. Quantum. química** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) junto con la plataforma de Química computacional de NWChem y cómo instalar las `qdk-chem` herramientas de línea de comandos para trabajar con datos de química de Quantum.</span><span class="sxs-lookup"><span data-stu-id="91c73-119">For example, the [chemistry library installation instructions](xref:microsoft.quantum.chemistry.concepts.installation) describe how to use the [**Microsoft.Quantum.Chemistry** package](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) together with the NWChem computational chemistry platform, and how to install the `qdk-chem` command-line tools for working with quantum chemistry data.</span></span>

## <a name="no-locq-command-line-applications-or-net-interopability"></a>[<span data-ttu-id="91c73-120">Q#aplicaciones de línea de comandos o interoperabilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="91c73-120">Q# command-line applications or .NET interopability</span></span>](#tab/tabid-csproj)

<span data-ttu-id="91c73-121">**Línea de comandos o Visual Studio Code:** Con la línea de comandos por su cuenta o desde Visual Studio Code, puede usar el `dotnet` comando para agregar una referencia de paquete NuGet al proyecto.</span><span class="sxs-lookup"><span data-stu-id="91c73-121">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add a NuGet package reference to your project.</span></span>
<span data-ttu-id="91c73-122">Por ejemplo, para agregar el paquete [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) , ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="91c73-122">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

<span data-ttu-id="91c73-123">**Visual Studio:** Si usa Visual Studio 2019 o una versión posterior, puede agregar paquetes adicionales Q# mediante el administrador de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="91c73-123">**Visual Studio:** If you are using Visual Studio 2019 or later, you can add additional Q# packages using the NuGet Package Manager.</span></span>
<span data-ttu-id="91c73-124">Para cargar un paquete:</span><span class="sxs-lookup"><span data-stu-id="91c73-124">To load a package:</span></span> 
1. <span data-ttu-id="91c73-125">Con un proyecto abierto en Visual Studio, seleccione **administrar paquetes NuGet...** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="91c73-125">With a project open in Visual Studio, select **Manage NuGet Packages...** from the **Project** menu.</span></span>

2. <span data-ttu-id="91c73-126">Haga clic en **examinar**, seleccione **incluir versión preliminar** y busque el nombre del paquete "Microsoft. Quantum. Numerics".</span><span class="sxs-lookup"><span data-stu-id="91c73-126">Click **Browse**, select **Include prerelease** and search for the package name "Microsoft.Quantum.Numerics".</span></span> <span data-ttu-id="91c73-127">Se enumerarán los paquetes disponibles para su descarga.</span><span class="sxs-lookup"><span data-stu-id="91c73-127">This will list the packages available for download.</span></span>

3. <span data-ttu-id="91c73-128">Mantenga el mouse sobre **Microsoft. Quantum. Numerics** y haga clic en la flecha hacia abajo situada a la derecha del número de versión para instalar el paquete de valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="91c73-128">Hover over **Microsoft.Quantum.Numerics** and click the downward-pointing arrow to the right of the version number to install the numerics package.</span></span>

<span data-ttu-id="91c73-129">Para obtener más información, vea la guía de la [interfaz de usuario del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="91c73-129">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="91c73-130">Como alternativa, puede usar la consola del administrador de paquetes para agregar la biblioteca de valores numéricos al proyecto a través de la interfaz de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="91c73-130">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Usar la consola del administrador de paquetes desde la línea de comandos](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="91c73-132">En la consola del administrador de paquetes, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91c73-132">From the Package Manager Console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="91c73-133">Para obtener más información, consulte la guía de la [consola del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="91c73-133">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

## <a name="ino-locq-notebooks"></a>[<span data-ttu-id="91c73-134">I Q# notebooks</span><span class="sxs-lookup"><span data-stu-id="91c73-134">IQ# Notebooks</span></span>](#tab/tabid-notebook)

<span data-ttu-id="91c73-135">Puede hacer que los paquetes adicionales estén disponibles para su uso en un bloc de notas de I Q# mediante el [ `%package` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="91c73-135">You can make additional packages available for use in an IQ# Notebook by using the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="91c73-136">Por ejemplo, para agregar el paquete [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) para su uso en un Q# Bloc de notas I, ejecute el siguiente comando en una celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="91c73-136">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following command in a notebook cell:</span></span>

```
%package Microsoft.Quantum.Numerics
```

<span data-ttu-id="91c73-137">Después de este comando, el paquete está disponible para todas las celdas del Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="91c73-137">Following this command, the package is available to any cells within the notebook.</span></span>
<span data-ttu-id="91c73-138">Para que el paquete esté disponible desde Q# el código en el área de trabajo actual, vuelva a cargar el área de trabajo después de agregar el paquete:</span><span class="sxs-lookup"><span data-stu-id="91c73-138">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```
%workspace reload
```

## <a name="python-interoperability"></a>[<span data-ttu-id="91c73-139">Interoperabilidad de Python</span><span class="sxs-lookup"><span data-stu-id="91c73-139">Python interoperability</span></span>](#tab/tabid-python)


<span data-ttu-id="91c73-140">Puede hacer que los paquetes adicionales estén disponibles para su uso en un programa host de Python mediante el [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) método.</span><span class="sxs-lookup"><span data-stu-id="91c73-140">You can make additional packages available for use in a Python host program by using the [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) method.</span></span>
<span data-ttu-id="91c73-141">Por ejemplo, para agregar el paquete [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) para su uso en un Q# Bloc de notas I, ejecute el siguiente código de Python:</span><span class="sxs-lookup"><span data-stu-id="91c73-141">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following Python code:</span></span>

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

<span data-ttu-id="91c73-142">Después de este comando, el paquete estará disponible para cualquier Q# código compilado mediante `qsharp.compile` .</span><span class="sxs-lookup"><span data-stu-id="91c73-142">Following this command, the package will be made available to any Q# code compiled using `qsharp.compile`.</span></span>
<span data-ttu-id="91c73-143">Para que el paquete esté disponible desde Q# el código en el área de trabajo actual, vuelva a cargar el área de trabajo después de agregar el paquete:</span><span class="sxs-lookup"><span data-stu-id="91c73-143">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```python
qsharp.reload()
```

***
