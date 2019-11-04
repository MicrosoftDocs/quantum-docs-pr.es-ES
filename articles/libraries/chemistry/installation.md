---
title: Instalación y validación de la biblioteca de química | Microsoft Docs
description: Instalación y validación de la biblioteca de química
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: fd43c783fa82c7219e143a57759919606fdd197f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184209"
---
# <a name="chemistry-library-installation-and-validation"></a>Instalación y validación de la biblioteca de química

El kit de desarrollo de Quantum proporciona compatibilidad con aplicaciones de química de Quantum a través del paquete de NuGet [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) .
Al igual que con otros paquetes NuGet, es sencillo agregar la biblioteca de química a su proyecto.

**Visual Studio 2019:** Si usa Visual Studio 2019, puede Agregar los paquetes de Quantum química mediante el administrador de paquetes NuGet.
Para abrir el administrador de paquetes, haga clic con el botón derecho en el proyecto al que desea agregar la biblioteca de química y seleccione "administrar paquetes NuGet...", como se muestra en la captura de pantalla siguiente.

![](~/media/vs2017-nuget-manage-packages.png)

En la pestaña examinar, busque el nombre del paquete "Microsoft. Quantum. química".

> [!NOTE]
> Asegúrese de marcar "incluir versión preliminar".

![](~/media/vs2017-nuget-package-search.png)

Se enumerarán los paquetes disponibles para su descarga.
Haga clic en "Microsoft. Quantum. química en el panel izquierdo, seleccione la última versión preliminar en el panel derecho y haga clic en" instalar ":

![](~/media/vs2017-nuget-select-chem.png)

Para obtener más información, vea la guía de la [interfaz de usuario del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Como alternativa, puede usar la consola del administrador de paquetes para agregar la biblioteca de química de Quantum al proyecto con una interfaz de línea de comandos.

![](~/media/vs2017-nuget-console-menu.png)

En la consola del administrador de paquetes, ejecute lo siguiente:

```
Install-Package Microsoft.Quantum.Chemistry
```

Para obtener más información, consulte la guía de la [consola del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Línea de comandos o Visual Studio Code:** Con la línea de comandos por su cuenta o desde Visual Studio Code, puede usar el comando `dotnet` para agregar una referencia de paquete NuGet al proyecto:

```bash
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>Comprobación de la instalación 

Al igual que el resto del kit de desarrollo de Quantum, la biblioteca de química de Quantum incluye una serie de ejemplos totalmente documentados para ayudarle a ponerse en marcha rápidamente.
Para probar la instalación con estos ejemplos, Clone el [repositorio de ejemplos principal](https://github.com/Microsoft/Quantum)y, a continuación, ejecute uno de los ejemplos.  Por ejemplo, para ejecutar el ejemplo [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Chemistry/MolecularHydrogen
dotnet run
```

Para comprobar la instalación de la biblioteca de química de Quantum mediante Microsoft Visual Studio después de clonar el repositorio:
    1. Abra la solución ChemistrySamples. sln en la carpeta química.  
    2. Seleccione samples/1. Moléculas simples/MolecularHydrogen como proyecto de inicio.
    3. Presione F5 para ejecutar la demostración de estimación de la fase de hidrógeno molecular.

Vea [obtener estimaciones de nivel de energía](xref:microsoft.quantum.chemistry.examples.energyestimate) para obtener más información sobre la estimación de los valores de los niveles de energía.   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>Uso del kit de desarrollo de Quantum con NWChem ##

El ejemplo MolecularHydrogen usa datos de entrada moleculares que se configuran manualmente.  Aunque esto es adecuado para pequeños ejemplos, la química de Quantum a escala requiere Hamiltonians con millones o miles de millones de términos. Tales Hamiltonians, generados por paquetes de química de cálculo escalables, son demasiado grandes para importarlos a mano. 

La biblioteca de química de Quantum para el kit de desarrollo de Quantum está diseñada para funcionar bien con paquetes de Química computacional, en particular la plataforma Química computacional de [**NWChem**](http://www.nwchem-sw.org/) desarrollada por el laboratorio de Ciencias moleculares del entorno ( EMSL) en el laboratorio nacional noroccidental del Pacífico.
En concreto, el paquete de `Microsoft.Quantum.Chemistry` proporciona herramientas para cargar instancias de problemas de simulación de química de Quantum representadas en el [esquema de Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), que también se admiten para la exportación de versiones recientes de NWChem.

Para empezar a trabajar con NWChem junto con el kit de desarrollo de Quantum, se recomienda uno de los métodos siguientes:
- Comience a usar los archivos de Broombridge existentes que se proporcionan con los ejemplos en [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).
- Use el [generador de flechas emsl para el Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , que es un front-end basado en web para NWChem, para generar nuevos archivos de entrada molecular con formato Broombridge.  
- Use la [imagen de Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) que proporciona PNNL para ejecutar NWChem, o bien
- [Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) para la plataforma.

Consulte de un [extremo a otro con NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) para más información sobre cómo trabajar con NWChem en modelos químicos para analizar con la biblioteca de química del kit de desarrollo de Quantum.

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Introducción al uso de archivos Broombridge proporcionados con los ejemplos
La carpeta [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) del repositorio de ejemplos del kit de desarrollo de Quantum contiene archivos de datos de moléculas con formato Broombridge.  

Como ejemplo sencillo, use el ejemplo de la biblioteca de química, [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) para cargar el Hamiltonian de uno de los archivos de Broombridge y realizar estimaciones de las puertas de la simulación de Quantum algorigthms:

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Vea [cargar un Hamiltonian desde un archivo](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) para obtener más información sobre cómo escribir moléculas representadas por el esquema Broombridge.  

Consulte [obtención de recuentos de recursos](xref:microsoft.quantum.chemistry.examples.resourcecounts) para más información sobre la estimación de recursos.  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>Introducción al uso del generador de flechas EMSL

EMSL flechas es una herramienta que usa bases de datos de cálculo de NWChem y química para generar datos de moléculas.  El [generador de flechas emsl para el Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) le permite especificar el modelo mediante varios generadores de modelos moleculares y generar el archivo de de Broombridge que va a usar el kit de desarrollo de Quantum.  

En la página EMSL, haga clic en la pestaña [' instrucciones '] y siga las instrucciones de [' ejemplos simples '] para generar archivos Broombridge.  Después, intente ejecutar [' GetGateCount '] para ver las estimaciones de recursos Quantum para estas moléculas.

### <a name="installing-nwchem-from-source"></a>Instalación de NWChem desde el origen

[PNNL proporciona](http://www.nwchem-sw.org/index.php/Compiling_NWChem)instrucciones completas sobre cómo instalar NWChem desde el origen.

> [!TIP]
> Si quiere usar NWChem desde Windows 10, el subsistema de Windows para Linux es una excelente opción.
> Una vez que haya instalado [Ubuntu 18,04 LTS para Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), ejecute `ubuntu18.04` desde su terminal favorito y siga las instrucciones anteriores para instalar NWChem desde el origen.

Una vez que haya compilado NWChem desde el origen, puede ejecutar el script de `yaml_driver` proporcionado con NWChem para generar rápidamente instancias de Broombridge a partir de las Barajas de entrada NWChem:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Este comando creará un nuevo archivo de `input.yaml` en el formato Broombridge en el directorio actual.

### <a name="using-nwchem-with-docker"></a>Uso de NWChem con Docker

Las imágenes pregeneradas para usar NWChem están disponibles entre plataformas a través de [Docker Hub](https://hub.docker.com).
Para empezar, siga las instrucciones de instalación de Docker para su plataforma:

- [Instalación de Docker para Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Instalación de Docker para macOS](https://docs.docker.com/docker-for-mac/install/)
- [Instalar Docker para Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Si usa Docker para Windows, debe compartir la unidad que contiene el directorio temporal (normalmente es la unidad `C:\`) con el demonio de Docker. Consulte la [documentación de Docker](https://docs.docker.com/docker-for-windows/#shared-drives) para obtener más detalles.

Una vez que tenga instalado Docker, puede usar el módulo de PowerShell que se proporciona con los ejemplos del kit de desarrollo de Quantum para ejecutar la imagen, o bien puede ejecutar la imagen manualmente.
Aquí se explica el uso de PowerShell. Si desea usar la imagen de Docker manualmente, consulte la documentación que se [proporciona con la imagen](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Ejecución de NWChem a través de PowerShell Core

Para usar la imagen de Docker de NWChem con el kit de desarrollo de Quantum, proporcionamos un pequeño módulo de PowerShell que controla el traslado de archivos dentro y fuera de NWChem.
Si aún no tiene PowerShell Core instalado, puede descargarlo entre plataformas desde el [repositorio de PowerShell en github](https://github.com/PowerShell/PowerShell#get-powershell).

> [!NOTE]
> PowerShell Core también se usa en algunos ejemplos para demostrar la interoperabilidad con los flujos de trabajo de ciencia de datos y análisis de negocios.

Una vez que tenga PowerShell Core instalado, importe `InvokeNWChem.psm1` para que los comandos de NWChem estén disponibles en la sesión actual:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

Esto hará que el comando `Convert-NWChemToBroombridge` esté disponible en la sesión actual de PowerShell.
Para descargar las imágenes necesarias de Docker y usarlas para ejecutar las Barajas de entrada de NWChem y capturar la salida en Broombridge, ejecute lo siguiente:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Se creará un archivo Broombridge ejecutando NWChem en `input.nw`.
De forma predeterminada, la salida de Broombridge tendrá el mismo nombre y la misma ruta de acceso que la baraja de entrada, con la extensión `.nw` reemplazada por `.yaml`.
Esto se puede invalidar mediante el parámetro `-DestinationPath` para `Convert-NWChemToBroombridge`.
Puede obtener más información mediante el uso de la funcionalidad de ayuda integrada de PowerShell:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```


