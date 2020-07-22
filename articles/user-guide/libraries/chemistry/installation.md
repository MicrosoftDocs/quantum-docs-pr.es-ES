---
title: 'Instalación de la biblioteca de Microsoft Q # química'
description: Aprenda a instalar la biblioteca de química de Microsoft Quantum y a usarla con la plataforma de Química computacional de NWChem.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 0e870bb3421dddb632375a2fc8633249954f8c8b
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871541"
---
# <a name="chemistry-library-installation"></a>Instalación de la biblioteca de química

El [ejemplo **MolecularHydrogen** ](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) usa datos de entrada moleculares que se configuran manualmente.
Aunque esto es adecuado para pequeños ejemplos, la química de Quantum a escala requiere Hamiltonians con millones o miles de millones de términos.
Tales Hamiltonians, generados por paquetes de Química computacional escalables, son demasiado grandes para importarlos manualmente.

La biblioteca de química de Quantum para el kit de desarrollo de Quantum se ha diseñado para funcionar bien con paquetes de Química computacional, en particular la plataforma química de cómputo de [**NWChem**](http://www.nwchem-sw.org/) desarrollada por el laboratorio de Ciencias moleculares del entorno (emsl) en el laboratorio nacional de Asia noroccidental.
En concreto, el [paquete **Microsoft. Quantum. química** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) proporciona herramientas para cargar instancias de problemas de simulación de química de Quantum representados en el [esquema de Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), que también se admiten para la exportación de versiones recientes de NWChem.

La biblioteca de química del kit de desarrollo de Quantum también proporciona una herramienta de línea de comandos, `qdk-chem` , para la conversión entre formatos heredados y [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

En esta sección se detalla cómo usar el kit de desarrollo de Quantum con NWChem y Broombridge, o con formatos heredados y `qdk-chem` .

## <a name="using-the-quantum-development-kit-with-nwchem"></a>Uso del kit de desarrollo de Quantum con NWChem

Para empezar a trabajar con NWChem junto con el kit de desarrollo de Quantum, use uno de los métodos siguientes:

- Comience a usar los archivos de Broombridge existentes que se proporcionan con los ejemplos en [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).
- Use el [generador de flechas emsl para el Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , que es un front-end basado en web para NWChem, para generar nuevos archivos de entrada molecular con formato Broombridge.  
- Use la [imagen de Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) que proporciona PNNL para ejecutar NWChem, o bien
- [Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) para la plataforma.

Consulte de un [extremo a otro con NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) para más información sobre cómo trabajar con NWChem en modelos químicos para analizar con la biblioteca de química del kit de desarrollo de Quantum.

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Introducción al uso de archivos Broombridge proporcionados con los ejemplos

La carpeta [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) del repositorio de ejemplos del kit de desarrollo de Quantum contiene archivos de datos de moléculas con formato Broombridge.  

Como ejemplo sencillo, use el ejemplo de la biblioteca de química, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) para cargar el Hamiltonian de uno de los archivos de Broombridge y realizar estimaciones de las puertas de la simulación de Quantum algorigthms:

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

Una vez que haya compilado NWChem desde el origen, puede ejecutar el `yaml_driver` script proporcionado con NWChem para generar rápidamente instancias de Broombridge a partir de las Barajas de entrada de NWChem:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Este comando creará un nuevo `input.yaml` archivo en el formato Broombridge en el directorio actual.

### <a name="using-nwchem-with-docker"></a>Uso de NWChem con Docker

Las imágenes pregeneradas para usar NWChem están disponibles entre plataformas a través de [Docker Hub](https://hub.docker.com).
Para empezar, siga las instrucciones de instalación de Docker para su plataforma:

- [Instalación de Docker para Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Instalación de Docker para macOS](https://docs.docker.com/docker-for-mac/install/)
- [Instalar Docker para Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Si usa Docker para Windows, debe compartir la unidad que contiene el directorio temporal (normalmente es la `C:\` unidad) con el demonio de Docker. Consulte la [documentación de Docker](https://docs.docker.com/docker-for-windows/#shared-drives) para obtener más detalles.

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

Esto hará que el `Convert-NWChemToBroombridge` comando esté disponible en la sesión actual de PowerShell.
Para descargar las imágenes necesarias de Docker y usarlas para ejecutar las Barajas de entrada de NWChem y capturar la salida en Broombridge, ejecute lo siguiente:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Se creará un archivo Broombridge ejecutando NWChem en `input.nw` .
De forma predeterminada, la salida de Broombridge tendrá el mismo nombre y la misma ruta de acceso que la baraja de entrada, con la `.nw` extensión reemplazada por `.yaml` .
Esto se puede invalidar mediante el `-DestinationPath` parámetro en `Convert-NWChemToBroombridge` .
Puede obtener más información mediante el uso de la funcionalidad de ayuda integrada de PowerShell:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```

## <a name="using-the-quantum-development-kit-with-qdk-chem"></a>Uso del kit de desarrollo de Quantum con`qdk-chem`

Para instalar `qdk-chem` , puede usar el SDK de .net Core en la línea de comandos:

```dotnetcli
dotnet tool install --global Microsoft.Quantum.Chemistry.Tools
```

Una vez que haya instalado `qdk-chem` , puede usar la `--help` opción para obtener más detalles sobre la funcionalidad que ofrece la `qdk-chem` herramienta.

Para convertir a y desde Broombridge, puede usar el `qdk-chem convert` comando:

```
qdk-chem convert --from fcidump --to broombridge data.fcidump --out data.yml
```

El `qdk-chem convert` comando también puede aceptar sus datos de la entrada estándar y puede escribir en la salida estándar; esto es especialmente útil en scripts y para la integración con herramientas que exportan a formatos heredados.
Por ejemplo, en Bash:

```bash
cat data.fcidump | qdk-convert --from fcidump --to broombridge - > data.yml
```
