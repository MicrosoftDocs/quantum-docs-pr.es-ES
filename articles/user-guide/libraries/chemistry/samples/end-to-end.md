---
title: Programa Quantum de ejemplo NWChem
description: Con una baraja de entrada de NWChem, recorra un ejemplo de obtención de recuentos de puertas para la simulación de química de Quantum.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 7605676e05ee352e47791657eeaafceef5dbb493
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275261"
---
# <a name="end-to-end-with-nwchem"></a>De un extremo a otro con NWChem #

En este artículo, le guiará a través de un ejemplo de cómo obtener recuentos de puertas para la simulación de química de Quantum, empezando por una baraja de entrada de [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) .
Antes de continuar con este ejemplo, asegúrese de que ha instalado Docker, siguiendo la [Guía de instalación y validación](xref:microsoft.quantum.chemistry.concepts.installation).

Para obtener más información:
- [Estructura de las Barajas de entrada de NWChem](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Comandos de presentación de entrada para su uso con el kit de desarrollo de Quantum](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [Instalación de la biblioteca de química y las dependencias](xref:microsoft.quantum.chemistry.concepts.installation)
- [Recuento de recursos](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> En este ejemplo se requiere la ejecución de Windows PowerShell Core.
> Descargue PowerShell Core para Windows, macOS o Linux en https://github.com/PowerShell/PowerShell .

## <a name="importing-required-powershell-modules"></a>Importación de los módulos de PowerShell necesarios ##

Si aún no lo ha hecho, Clone el [repositorio Microsoft/Quantum](https://github.com/Microsoft/Quantum), que contiene ejemplos y utilidades para trabajar con el kit de desarrollo de Quantum:

```powershell
git clone https://github.com/Microsoft/Quantum
```

Una vez clonado `Microsoft/Quantum` , ejecute `cd` en la `utilities/` carpeta e importe el módulo de PowerShell para trabajar con Docker y NWChem:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> De forma predeterminada, Windows impide la ejecución de cualquier script o módulo como medida de seguridad.
> Para permitir que los módulos como `Invoke-NWChem.psm1` se ejecuten en Windows, es posible que tenga que cambiar la Directiva de ejecución.
> Para ello, ejecute el `Set-ExecutionPolicy` comando:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> La Directiva de ejecución se revertirá al salir de PowerShell.
> Si desea guardar la Directiva de ejecución, use un valor diferente para `-Scope` :
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

Ahora debería tener el `Convert-NWChemToBroombridge` comando disponible:

```powershell
Get-Command -Module InvokeNWChem
```

A continuación, importaremos el `Get-GateCount` comando proporcionado con el ejemplo **GetGateCount** .
Para obtener información completa, consulte las [instrucciones proporcionadas con el ejemplo](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/GetGateCount).
A continuación, ejecute lo siguiente y sustituya `<runtime>` por `win10-x64` , `osx-x64` o `linux-x64` , según el sistema operativo:

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

Ahora debería tener el `Get-GateCount` comando disponible:

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Barajas de entrada ##

El paquete NWChem toma un archivo de texto denominado _baraja_ que especifica un problema de química de Quantum que se va a resolver, junto con otros parámetros, como la configuración de la asignación de memoria.
En este ejemplo, usaremos una de las cubiertas de entrada predefinidas que se incluyen en NWChem.
En primer lugar, Clone el [repositorio nwchemgit/NWChem](https://github.com/nwchemgit/nwchem):

> [!NOTE]
> Dado que se trata de un repositorio muy grande, podemos hacer un clon superficial para ahorrar espacio de disco y ancho de banda, mediante el `--depth 1` argumento.
> Sin embargo, esto es opcional.
> La clonación funcionará perfectamente sin `--depth 1` .

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

El `nwchemgit/nwchem` repositorio incluye una variedad de Barajas de entrada para su uso con el kit de desarrollo de Quantum, que se muestra en la [ `QA/chem_library_tests` carpeta](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).
En este ejemplo, usaremos la `H4` baraja de entrada:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

La molécula en cuestión es un sistema de 4 átomos de hidrógeno que se organizan en una determinada geometría que depende de un ángulo, el parámetro, `alpha` tal como se indica en el nombre `h4_sto6g_alpha.nw` de la baraja. H4 es un [Benchmark molecular](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) conocido para la Química computacional desde la década de 1970. El parámetro `sto6g` es indicativo de que la baraja implementa una representación con respecto a un Slater de tipo orbital, en concreto, una representación con respecto a un [conjunto de ALM-GN](https://en.wikipedia.org/wiki/STO-nG_basis_sets) con 6 funciones de base de gaussiano. Esta baraja de entrada contiene además varias instrucciones para el motor de contracción de NWChem tensores (TCE) que dirigen NWChem para generar la información necesaria para interoperar con el kit de desarrollo de Quantum:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>Generar y consumir la salida de Broombridge desde NWChem ##

Ahora tiene todo lo que necesita para generar y consumir documentos de Broombridge.
Para ejecutar NWChem y generar un documento de Broombridge para la `h4_sto6g_0.000.nw` baraja de entrada, ejecute `Convert-NWChemToBroombridge` :

> [!NOTE]
> La primera vez que ejecute este comando, Docker descargará la `nwchemorg/nwchem-qc` imagen.
> Esto puede tardar unos minutos, en función de la velocidad de conexión, lo que podría proporcionar una oportunidad para obtener una taza de café.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Esto producirá un documento Broombridge denominado `h4_sto6g_0.000.yaml` que puede usar con `Get-GateCount` :

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

Ahora debería ver la salida de la consola que contiene la estimación de recursos, como el recuento de T, el número de giros, el recuento de CNOT, etc. para varios métodos de simulación de Quantum:

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

Hay muchas cosas que debe hacer desde aquí: 
- Pruebe diferentes Barajas de entrada predefinidas, por ejemplo, mediante la modificación del parámetro `alpha` en. `h4_sto6g_alpha.nw` 
- Pruebe a modificar las Barajas editando directamente las Barajas de NWChem, por ejemplo, explorando `STO-nG` modelos para distintas opciones de n. 
- Pruebe otras Barajas de entrada NWChem predefinidas que están disponibles `nwchem/qa/chem_library_tests` en.
- Pruebe un conjunto de pruebas comparativas predefinidas de Broombridge YAML que se generaron a partir de NWChem y que están disponibles como parte del [repositorio Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML). Estas pruebas comparativas incluyen: 
    - moléculas pequeñas como el hidrógeno molecular (H2), Beryllium (ser), litio hidruro (LiH),
    - moléculas mayores como ozono (O3), beta-Carotene, cytosine y muchas más. 
- Pruebe las flechas gráficas de [emsl](https://arrows.emsl.pnnl.gov/api/qsharp_chem) de front-end que incluye una interfaz en el Microsoft Quantum Development Kit. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>Generar Broombridge salida de EMSL flechas ##

Para empezar a trabajar con las flechas de EMSL de front-end basadas en Web, vaya a un explorador [aquí](https://arrows.emsl.pnnl.gov/api/qsharp_chem). 

> [!NOTE]
> La ejecución de flechas EMSL en un explorador Web requiere que JavaScript esté habilitado. Consulte estas [instrucciones](https://www.enable-javascript.com/) para habilitar JavaScript en el explorador. 

En primer lugar, escriba una molécula en el cuadro de consulta que indica``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

Puede escribir muchas moléculas por su nombre de uso coloquial, como "cafeína" en lugar de "1, 3, 7-Trimethylxanthine". 

A continuación, haga clic en el botón que indica ``theory{qsharp_chem}`` . Esto rellenará el cuadro consulta con una instrucción que indicará a la ejecución que exporte la salida en el formato Broombridge YAML. 

Ahora, reloj ``Run Arrows`` . Dependiendo del tamaño de la entrada, esto puede tardar unos minutos. O bien, en el caso de que el modelo determinado ya se haya calculado antes, se puede realizar con mucha rapidez, ya que solo se realizará una búsqueda en una base de datos. En cualquier caso, se le dirigirá a una nueva página que contiene una gran cantidad de información sobre la ejecución determinada de NWChem en la baraja especificada por la entrada. 

Puede descargar y guardar el archivo Broombridge YAML de la sección que comienza con el siguiente encabezado: 
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

Haga clic en activado ``download`` , que guarda una copia local con un nombre de archivo único como ``qsharp_chem48443.yaml`` (el nombre concreto será diferente para cada ejecución). Después, puede procesar este archivo como se indica anteriormente, por ejemplo, con 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
para obtener recuentos de recursos. 

Podría disfrutar del generador de moléculas 3D al que se puede tener acceso desde la ``Arrows Entry - 3D Builder`` pestaña de la página de inicio de las flechas de emsl. Al hacer clic en la imagen 3D de [JSMol](http://wiki.jmol.org/index.php/JSmol) de la molécula mostrada, se le permitirá editarla. Puede mover los átomos alrededor de, arrastrando los átomos para que sus distancias entre moleculares cambien, agreguen o quiten átomos, etc. Para cada una de estas opciones, una vez que haya agregado ``theory{qsharp_chem}`` en el cuadro consulta, puede generar una instancia del esquema YAML de Broombridge y explorarlo en profundidad con la biblioteca de química de Quantum. 
