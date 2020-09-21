---
title: Programa Quantum de ejemplo NWChem
description: Con una baraja de entrada de NWChem, recorra un ejemplo de obtención de recuentos de puertas para la simulación de química de Quantum.
author: cgranade
ms.author: chgranad
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
no-loc:
- Q#
- $$v
ms.openlocfilehash: 986ff2c2ff144c57bd01ddeea0467d0168fd9334
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835764"
---
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="6b9c2-103">De un extremo a otro con NWChem</span><span class="sxs-lookup"><span data-stu-id="6b9c2-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="6b9c2-104">En este artículo, le guiará a través de un ejemplo de cómo obtener recuentos de puertas para la simulación de química de Quantum, empezando por una baraja de entrada de [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) .</span><span class="sxs-lookup"><span data-stu-id="6b9c2-104">In this article, you will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="6b9c2-105">Antes de continuar con este ejemplo, asegúrese de que ha instalado Docker, siguiendo la [Guía de instalación y validación](xref:microsoft.quantum.chemistry.concepts.installation).</span><span class="sxs-lookup"><span data-stu-id="6b9c2-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="6b9c2-106">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-106">For more information:</span></span>
- [<span data-ttu-id="6b9c2-107">Estructura de las Barajas de entrada de NWChem</span><span class="sxs-lookup"><span data-stu-id="6b9c2-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="6b9c2-108">Comandos de presentación de entrada para su uso con el kit de desarrollo de Quantum</span><span class="sxs-lookup"><span data-stu-id="6b9c2-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/main/contrib/quasar)
- [<span data-ttu-id="6b9c2-109">Instalación de la biblioteca de química y las dependencias</span><span class="sxs-lookup"><span data-stu-id="6b9c2-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="6b9c2-110">Recuento de recursos</span><span class="sxs-lookup"><span data-stu-id="6b9c2-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="6b9c2-111">En este ejemplo se requiere la ejecución de Windows PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="6b9c2-112">Descargue PowerShell Core para Windows, macOS o Linux en https://github.com/PowerShell/PowerShell .</span><span class="sxs-lookup"><span data-stu-id="6b9c2-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="6b9c2-113">Importación de los módulos de PowerShell necesarios</span><span class="sxs-lookup"><span data-stu-id="6b9c2-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="6b9c2-114">Si aún no lo ha hecho, Clone el [repositorio Microsoft/Quantum](https://github.com/Microsoft/Quantum), que contiene ejemplos y utilidades para trabajar con el kit de desarrollo de Quantum:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="6b9c2-115">Una vez clonado `Microsoft/Quantum` , ejecute `cd` en la `utilities/` carpeta e importe el módulo de PowerShell para trabajar con Docker y NWChem:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="6b9c2-116">De forma predeterminada, Windows impide la ejecución de los scripts o módulos como medida de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-116">By default, Windows prevents the running of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="6b9c2-117">Para permitir que los módulos como `Invoke-NWChem.psm1` se ejecuten en Windows, es posible que deba cambiar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the policy.</span></span>
> <span data-ttu-id="6b9c2-118">Para ello, ejecute el `Set-ExecutionPolicy` comando:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="6b9c2-119">La Directiva se revertirá al salir de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-119">The policy will revert when you exit PowerShell.</span></span>
> <span data-ttu-id="6b9c2-120">Si desea guardar la Directiva, use un valor diferente para `-Scope` :</span><span class="sxs-lookup"><span data-stu-id="6b9c2-120">If you would like to save the policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="6b9c2-121">Ahora debería tener el `Convert-NWChemToBroombridge` comando disponible:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="6b9c2-122">A continuación, importaremos el `Get-GateCount` comando proporcionado con el ejemplo **GetGateCount** .</span><span class="sxs-lookup"><span data-stu-id="6b9c2-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="6b9c2-123">Para obtener información completa, consulte las [instrucciones proporcionadas con el ejemplo](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount).</span><span class="sxs-lookup"><span data-stu-id="6b9c2-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount).</span></span>
<span data-ttu-id="6b9c2-124">A continuación, ejecute lo siguiente y sustituya `<runtime>` por `win10-x64` , `osx-x64` o `linux-x64` , según el sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="6b9c2-125">Ahora debería tener el `Get-GateCount` comando disponible:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="6b9c2-126">Barajas de entrada</span><span class="sxs-lookup"><span data-stu-id="6b9c2-126">Input Decks</span></span> ##

<span data-ttu-id="6b9c2-127">El paquete NWChem toma un archivo de texto denominado _baraja_ que especifica un problema de química de Quantum que se va a resolver, junto con otros parámetros, como la configuración de la asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="6b9c2-128">En este ejemplo, usaremos una de las cubiertas de entrada predefinidas que se incluyen en NWChem.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="6b9c2-129">En primer lugar, Clone el [repositorio nwchemgit/NWChem](https://github.com/nwchemgit/nwchem):</span><span class="sxs-lookup"><span data-stu-id="6b9c2-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="6b9c2-130">Dado que se trata de un repositorio muy grande, podemos hacer un clon superficial para ahorrar espacio de disco y ancho de banda, mediante el `--depth 1` argumento.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="6b9c2-131">Sin embargo, esto es opcional.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-131">This is optional, however.</span></span>
> <span data-ttu-id="6b9c2-132">La clonación funcionará perfectamente sin `--depth 1` .</span><span class="sxs-lookup"><span data-stu-id="6b9c2-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="6b9c2-133">El `nwchemgit/nwchem` repositorio incluye una variedad de Barajas de entrada para su uso con el kit de desarrollo de Quantum, que se muestra en la [ `QA/chem_library_tests` carpeta](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests).</span><span class="sxs-lookup"><span data-stu-id="6b9c2-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests).</span></span>
<span data-ttu-id="6b9c2-134">En este ejemplo, usaremos la `H4` baraja de entrada:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="6b9c2-135">La molécula en cuestión es un sistema de 4 átomos de hidrógeno que se organizan en una determinada geometría que depende de un ángulo, el parámetro, `alpha` tal como se indica en el nombre `h4_sto6g_alpha.nw` de la baraja.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="6b9c2-136">H4 es un [Benchmark molecular](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) conocido para la Química computacional desde la década de 1970.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="6b9c2-137">El parámetro `sto6g` es indicativo de que la baraja implementa una representación con respecto a un Slater de tipo orbital, en concreto, una representación con respecto a un [conjunto de ALM-GN](https://en.wikipedia.org/wiki/STO-nG_basis_sets) con 6 funciones de base de gaussiano.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="6b9c2-138">Esta baraja de entrada contiene además varias instrucciones para el motor de contracción de NWChem tensores (TCE) que dirigen NWChem para generar la información necesaria para interoperar con el kit de desarrollo de Quantum:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="6b9c2-139">Generar y consumir la salida de Broombridge desde NWChem</span><span class="sxs-lookup"><span data-stu-id="6b9c2-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="6b9c2-140">Ahora tiene todo lo que necesita para generar y consumir documentos de Broombridge.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-140">You now have everything you need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="6b9c2-141">Para ejecutar NWChem y generar un documento de Broombridge para la `h4_sto6g_0.000.nw` baraja de entrada, ejecute `Convert-NWChemToBroombridge` :</span><span class="sxs-lookup"><span data-stu-id="6b9c2-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="6b9c2-142">La primera vez que ejecute este comando, Docker descargará la `nwchemorg/nwchem-qc` imagen.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="6b9c2-143">Esto puede tardar unos minutos, en función de la velocidad de conexión, lo que podría proporcionar una oportunidad para obtener una taza de café.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="6b9c2-144">Esto producirá un documento Broombridge denominado `h4_sto6g_0.000.yaml` que puede usar con `Get-GateCount` :</span><span class="sxs-lookup"><span data-stu-id="6b9c2-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that you can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="6b9c2-145">Ahora debería ver la salida de la consola que contiene la estimación de recursos, como el recuento de T, el número de giros, el recuento de CNOT, etc. para varios métodos de simulación de Quantum:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

<span data-ttu-id="6b9c2-146">Hay muchas cosas que debe hacer desde aquí:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="6b9c2-147">Pruebe diferentes Barajas de entrada predefinidas, por ejemplo, mediante la modificación del parámetro `alpha` en. `h4_sto6g_alpha.nw`</span><span class="sxs-lookup"><span data-stu-id="6b9c2-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="6b9c2-148">Pruebe a modificar las Barajas editando directamente las Barajas de NWChem, por ejemplo, explorando `STO-nG` modelos para distintas opciones de n.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="6b9c2-149">Pruebe otras Barajas de entrada NWChem predefinidas que están disponibles `nwchem/qa/chem_library_tests` en.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="6b9c2-150">Pruebe un conjunto de pruebas comparativas predefinidas de Broombridge YAML que se generaron a partir de NWChem y que están disponibles como parte del [repositorio Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="6b9c2-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="6b9c2-151">Estas pruebas comparativas incluyen:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="6b9c2-152">moléculas pequeñas como el hidrógeno molecular (H2), Beryllium (ser), litio hidruro (LiH),</span><span class="sxs-lookup"><span data-stu-id="6b9c2-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="6b9c2-153">moléculas mayores como ozono (O3), beta-Carotene, cytosine y muchas más.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="6b9c2-154">Pruebe las flechas gráficas de [emsl](https://arrows.emsl.pnnl.gov/api/qsharp_chem) de front-end que incluye una interfaz en el Microsoft Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="6b9c2-155">Generar Broombridge salida de EMSL flechas</span><span class="sxs-lookup"><span data-stu-id="6b9c2-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="6b9c2-156">Para empezar a trabajar con las flechas de EMSL de front-end basadas en Web, vaya a un explorador [aquí](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span><span class="sxs-lookup"><span data-stu-id="6b9c2-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="6b9c2-157">La ejecución de flechas EMSL en un explorador Web requiere que JavaScript esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="6b9c2-158">Consulte estas [instrucciones](https://www.enable-javascript.com/) para habilitar JavaScript en el explorador.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="6b9c2-159">En primer lugar, escriba una molécula en el cuadro de consulta que indica ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="6b9c2-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="6b9c2-160">Puede escribir muchas moléculas por su nombre de uso coloquial, como "cafeína" en lugar de "1, 3, 7-Trimethylxanthine".</span><span class="sxs-lookup"><span data-stu-id="6b9c2-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="6b9c2-161">A continuación, haga clic en el botón que indica ``theory{qsharp_chem}`` .</span><span class="sxs-lookup"><span data-stu-id="6b9c2-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="6b9c2-162">Esto rellenará el cuadro consulta con una instrucción que indicará a la ejecución que exporte la salida en el formato Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="6b9c2-163">Ahora, reloj ``Run Arrows`` .</span><span class="sxs-lookup"><span data-stu-id="6b9c2-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="6b9c2-164">Dependiendo del tamaño de la entrada, esto puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="6b9c2-165">O bien, en el caso de que el modelo determinado ya se haya calculado antes, se puede realizar con mucha rapidez, ya que solo se realizará una búsqueda en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="6b9c2-166">En cualquier caso, se le dirigirá a una nueva página que contiene una gran cantidad de información sobre la ejecución determinada de NWChem en la baraja especificada por la entrada.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="6b9c2-167">Puede descargar y guardar el archivo Broombridge YAML de la sección que comienza con el siguiente encabezado:</span><span class="sxs-lookup"><span data-stu-id="6b9c2-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

<span data-ttu-id="6b9c2-168">Haga clic en activado ``download`` , que guarda una copia local con un nombre de archivo único como ``qsharp_chem48443.yaml`` (el nombre concreto será diferente para cada ejecución).</span><span class="sxs-lookup"><span data-stu-id="6b9c2-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="6b9c2-169">Después, puede procesar este archivo como se indica anteriormente, por ejemplo, con</span><span class="sxs-lookup"><span data-stu-id="6b9c2-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="6b9c2-170">para obtener recuentos de recursos.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-170">to get resource counts.</span></span> 

<span data-ttu-id="6b9c2-171">Podría disfrutar del generador de moléculas 3D al que se puede tener acceso desde la ``Arrows Entry - 3D Builder`` pestaña de la página de inicio de las flechas de emsl.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="6b9c2-172">Al hacer clic en la imagen 3D de [JSMol](http://wiki.jmol.org/index.php/JSmol) de la molécula mostrada, se le permitirá editarla.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="6b9c2-173">Puede mover los átomos alrededor de, arrastrando los átomos para que sus distancias entre moleculares cambien, agreguen o quiten átomos, etc. Para cada una de estas opciones, una vez que haya agregado ``theory{qsharp_chem}`` en el cuadro consulta, puede generar una instancia del esquema YAML de Broombridge y explorarlo en profundidad con la biblioteca de química de Quantum.</span><span class="sxs-lookup"><span data-stu-id="6b9c2-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 
