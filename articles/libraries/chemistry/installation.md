---
title: Instalación y validación de la biblioteca de química | Microsoft Docs
description: Instalación y validación de la biblioteca de química
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: de13d1814821c612ed74a347dc8ffb5881063576
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036481"
---
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="d5fc3-103">Instalación y validación de la biblioteca de química</span><span class="sxs-lookup"><span data-stu-id="d5fc3-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="d5fc3-104">El kit de desarrollo de Quantum proporciona compatibilidad con aplicaciones de química de Quantum a través del paquete de NuGet [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) .</span><span class="sxs-lookup"><span data-stu-id="d5fc3-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="d5fc3-105">Al igual que con otros paquetes NuGet, es sencillo agregar la biblioteca de química a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="d5fc3-106">**Visual Studio 2019:** Si usa Visual Studio 2019, puede Agregar los paquetes de Quantum química mediante el administrador de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="d5fc3-107">Para abrir el administrador de paquetes, haga clic con el botón derecho en el proyecto al que desea agregar la biblioteca de química y seleccione "administrar paquetes NuGet...", como se muestra en la captura de pantalla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="d5fc3-108">En la pestaña examinar, busque el nombre del paquete "Microsoft. Quantum. química".</span><span class="sxs-lookup"><span data-stu-id="d5fc3-108">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="d5fc3-109">Asegúrese de marcar "incluir versión preliminar".</span><span class="sxs-lookup"><span data-stu-id="d5fc3-109">Make sure to tick "Include prerelease."</span></span>

![](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="d5fc3-110">Se enumerarán los paquetes disponibles para su descarga.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-110">This will list the packages available for download.</span></span>
<span data-ttu-id="d5fc3-111">Haga clic en "Microsoft. Quantum. química en el panel izquierdo, seleccione la última versión preliminar en el panel derecho y haga clic en" instalar ":</span><span class="sxs-lookup"><span data-stu-id="d5fc3-111">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="d5fc3-112">Para obtener más información, vea la guía de la [interfaz de usuario del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="d5fc3-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="d5fc3-113">Como alternativa, puede usar la consola del administrador de paquetes para agregar la biblioteca de química de Quantum al proyecto con una interfaz de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-113">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="d5fc3-114">En la consola del administrador de paquetes, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="d5fc3-115">Para obtener más información, consulte la guía de la [consola del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="d5fc3-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="d5fc3-116">**Línea de comandos o Visual Studio Code:** Con la línea de comandos por su cuenta o desde Visual Studio Code, puede usar el comando `dotnet` para agregar una referencia de paquete NuGet al proyecto:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="d5fc3-117">Comprobación de la instalación</span><span class="sxs-lookup"><span data-stu-id="d5fc3-117">Verifying Your Installation</span></span> 

<span data-ttu-id="d5fc3-118">Al igual que el resto del kit de desarrollo de Quantum, la biblioteca de química de Quantum incluye una serie de ejemplos totalmente documentados para ayudarle a ponerse en marcha rápidamente.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-118">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="d5fc3-119">Para probar la instalación con estos ejemplos, Clone el [repositorio de ejemplos principal](https://github.com/Microsoft/Quantum)y, a continuación, ejecute uno de los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="d5fc3-120">Por ejemplo, para ejecutar el ejemplo [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) :</span><span class="sxs-lookup"><span data-stu-id="d5fc3-120">For example, to run the [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="d5fc3-121">Para comprobar la instalación de la biblioteca de química de Quantum mediante Microsoft Visual Studio después de clonar el repositorio:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-121">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="d5fc3-122">Abra la solución ChemistrySamples. sln en la carpeta química.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-122">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="d5fc3-123">Seleccione samples/1.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-123">Select Samples/1.</span></span> <span data-ttu-id="d5fc3-124">Moléculas simples/MolecularHydrogen como proyecto de inicio.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-124">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="d5fc3-125">Presione F5 para ejecutar la demostración de estimación de la fase de hidrógeno molecular.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-125">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="d5fc3-126">Vea [obtener estimaciones de nivel de energía](xref:microsoft.quantum.chemistry.examples.energyestimate) para obtener más información sobre la estimación de los valores de los niveles de energía.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-126">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="d5fc3-127">Uso del kit de desarrollo de Quantum con NWChem</span><span class="sxs-lookup"><span data-stu-id="d5fc3-127">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="d5fc3-128">El ejemplo MolecularHydrogen usa datos de entrada moleculares que se configuran manualmente.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-128">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="d5fc3-129">Aunque esto es adecuado para pequeños ejemplos, la química de Quantum a escala requiere Hamiltonians con millones o miles de millones de términos.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-129">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="d5fc3-130">Tales Hamiltonians, generados por paquetes de química de cálculo escalables, son demasiado grandes para importarlos a mano.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-130">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="d5fc3-131">La biblioteca de química de Quantum para el kit de desarrollo de Quantum se ha diseñado para funcionar bien con paquetes de Química computacional, en particular la plataforma química de cómputo de [**NWChem**](http://www.nwchem-sw.org/) desarrollada por el laboratorio de Ciencias moleculares del entorno (emsl) en el laboratorio nacional de Asia noroccidental.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-131">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="d5fc3-132">En concreto, el paquete de `Microsoft.Quantum.Chemistry` proporciona herramientas para cargar instancias de problemas de simulación de química de Quantum representadas en el [esquema de Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), que también se admiten para la exportación de versiones recientes de NWChem.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-132">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="d5fc3-133">Para empezar a trabajar con NWChem junto con el kit de desarrollo de Quantum, se recomienda uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-133">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="d5fc3-134">Comience a usar los archivos de Broombridge existentes que se proporcionan con los ejemplos en [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="d5fc3-134">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="d5fc3-135">Use el [generador de flechas emsl para el Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , que es un front-end basado en web para NWChem, para generar nuevos archivos de entrada molecular con formato Broombridge.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-135">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="d5fc3-136">Use la [imagen de Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) que proporciona PNNL para ejecutar NWChem, o bien</span><span class="sxs-lookup"><span data-stu-id="d5fc3-136">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="d5fc3-137">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) para la plataforma.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-137">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="d5fc3-138">Consulte de un [extremo a otro con NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) para más información sobre cómo trabajar con NWChem en modelos químicos para analizar con la biblioteca de química del kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-138">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="d5fc3-139">Introducción al uso de archivos Broombridge proporcionados con los ejemplos</span><span class="sxs-lookup"><span data-stu-id="d5fc3-139">Getting started using Broombridge files provided with the samples</span></span>

<span data-ttu-id="d5fc3-140">La carpeta [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) del repositorio de ejemplos del kit de desarrollo de Quantum contiene archivos de datos de moléculas con formato Broombridge.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-140">The [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="d5fc3-141">Como ejemplo sencillo, use el ejemplo de la biblioteca de química, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) para cargar el Hamiltonian de uno de los archivos de Broombridge y realizar estimaciones de las puertas de la simulación de Quantum algorigthms:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-141">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="d5fc3-142">Vea [cargar un Hamiltonian desde un archivo](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) para obtener más información sobre cómo escribir moléculas representadas por el esquema Broombridge.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-142">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="d5fc3-143">Consulte [obtención de recuentos de recursos](xref:microsoft.quantum.chemistry.examples.resourcecounts) para más información sobre la estimación de recursos.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-143">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="d5fc3-144">Introducción al uso del generador de flechas EMSL</span><span class="sxs-lookup"><span data-stu-id="d5fc3-144">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="d5fc3-145">EMSL flechas es una herramienta que usa bases de datos de cálculo de NWChem y química para generar datos de moléculas.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-145">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="d5fc3-146">El [generador de flechas emsl para el Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) le permite especificar el modelo mediante varios generadores de modelos moleculares y generar el archivo de de Broombridge que va a usar el kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-146">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="d5fc3-147">En la página EMSL, haga clic en la pestaña [' instrucciones '] y siga las instrucciones de [' ejemplos simples '] para generar archivos Broombridge.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-147">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="d5fc3-148">Después, intente ejecutar [' GetGateCount '] para ver las estimaciones de recursos Quantum para estas moléculas.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-148">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="d5fc3-149">Instalación de NWChem desde el origen</span><span class="sxs-lookup"><span data-stu-id="d5fc3-149">Installing NWChem from Source</span></span>

<span data-ttu-id="d5fc3-150">[PNNL proporciona](http://www.nwchem-sw.org/index.php/Compiling_NWChem)instrucciones completas sobre cómo instalar NWChem desde el origen.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-150">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="d5fc3-151">Si quiere usar NWChem desde Windows 10, el subsistema de Windows para Linux es una excelente opción.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-151">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="d5fc3-152">Una vez que haya instalado [Ubuntu 18,04 LTS para Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), ejecute `ubuntu18.04` desde su terminal favorito y siga las instrucciones anteriores para instalar NWChem desde el origen.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-152">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="d5fc3-153">Una vez que haya compilado NWChem desde el origen, puede ejecutar el script de `yaml_driver` proporcionado con NWChem para generar rápidamente instancias de Broombridge a partir de las Barajas de entrada NWChem:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-153">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="d5fc3-154">Este comando creará un nuevo archivo de `input.yaml` en el formato Broombridge en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-154">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="d5fc3-155">Uso de NWChem con Docker</span><span class="sxs-lookup"><span data-stu-id="d5fc3-155">Using NWChem with Docker</span></span>

<span data-ttu-id="d5fc3-156">Las imágenes pregeneradas para usar NWChem están disponibles entre plataformas a través de [Docker Hub](https://hub.docker.com).</span><span class="sxs-lookup"><span data-stu-id="d5fc3-156">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="d5fc3-157">Para empezar, siga las instrucciones de instalación de Docker para su plataforma:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-157">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="d5fc3-158">Instalación de Docker para Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d5fc3-158">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="d5fc3-159">Instalación de Docker para macOS</span><span class="sxs-lookup"><span data-stu-id="d5fc3-159">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="d5fc3-160">Instalar Docker para Windows 10</span><span class="sxs-lookup"><span data-stu-id="d5fc3-160">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="d5fc3-161">Si usa Docker para Windows, debe compartir la unidad que contiene el directorio temporal (normalmente es la unidad `C:\`) con el demonio de Docker.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-161">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="d5fc3-162">Consulte la [documentación de Docker](https://docs.docker.com/docker-for-windows/#shared-drives) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-162">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="d5fc3-163">Una vez que tenga instalado Docker, puede usar el módulo de PowerShell que se proporciona con los ejemplos del kit de desarrollo de Quantum para ejecutar la imagen, o bien puede ejecutar la imagen manualmente.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-163">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="d5fc3-164">Aquí se explica el uso de PowerShell. Si desea usar la imagen de Docker manualmente, consulte la documentación que se [proporciona con la imagen](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span><span class="sxs-lookup"><span data-stu-id="d5fc3-164">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="d5fc3-165">Ejecución de NWChem a través de PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="d5fc3-165">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="d5fc3-166">Para usar la imagen de Docker de NWChem con el kit de desarrollo de Quantum, proporcionamos un pequeño módulo de PowerShell que controla el traslado de archivos dentro y fuera de NWChem.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-166">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="d5fc3-167">Si aún no tiene PowerShell Core instalado, puede descargarlo entre plataformas desde el [repositorio de PowerShell en github](https://github.com/PowerShell/PowerShell#get-powershell).</span><span class="sxs-lookup"><span data-stu-id="d5fc3-167">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="d5fc3-168">PowerShell Core también se usa en algunos ejemplos para demostrar la interoperabilidad con los flujos de trabajo de ciencia de datos y análisis de negocios.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-168">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="d5fc3-169">Una vez que tenga PowerShell Core instalado, importe `InvokeNWChem.psm1` para que los comandos de NWChem estén disponibles en la sesión actual:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-169">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="d5fc3-170">Esto hará que el comando `Convert-NWChemToBroombridge` esté disponible en la sesión actual de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-170">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="d5fc3-171">Para descargar las imágenes necesarias de Docker y usarlas para ejecutar las Barajas de entrada de NWChem y capturar la salida en Broombridge, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-171">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="d5fc3-172">Se creará un archivo Broombridge ejecutando NWChem en `input.nw`.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-172">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="d5fc3-173">De forma predeterminada, la salida de Broombridge tendrá el mismo nombre y la misma ruta de acceso que la baraja de entrada, con la extensión `.nw` reemplazada por `.yaml`.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-173">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="d5fc3-174">Esto se puede invalidar mediante el parámetro `-DestinationPath` para `Convert-NWChemToBroombridge`.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-174">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="d5fc3-175">Puede obtener más información mediante el uso de la funcionalidad de ayuda integrada de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-175">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
