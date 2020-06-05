---
title: Notas de la versión del kit de desarrollo de Quantum
description: Obtenga información sobre las últimas actualizaciones de la versión preliminar del kit de desarrollo de Microsoft Quantum.
author: natke
ms.author: nakersha
ms.date: 09/30/2019
ms.topic: article
uid: microsoft.quantum.relnotes
ms.openlocfilehash: ec5b3b26102df6ecc19d89b41c7fd8938b34e761
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327771"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Notas de la versión de Microsoft Quantum Development Kit

Este artículo contiene información sobre cada versión de Quantum Development Kit.

Para obtener instrucciones de instalación, consulte la [guía de instalación](xref:microsoft.quantum.install).

Para obtener instrucciones de actualización, consulte la [guía de actualización](xref:microsoft.quantum.update).

## <a name="version-0112006207"></a>Versión 0.11.2006.207

*Fecha de lanzamiento: 3 de junio de 2020*

Esta versión contiene lo siguiente:

- Dejarán de producirse errores en los cuadernos de Q# y en los programas de host de Python cuando haya un punto de entrada de Q#
- Actualizaciones en la [biblioteca estándar](xref:microsoft.quantum.libraries.standard.intro) para poder usar modificadores de acceso
- Ahora, el compilador permite el complemento de los pasos de reescritura entre los pasos de reescritura integrados
- Se han quitado varias funciones y operaciones en desuso siguiendo la programación descrita en los [principios de la API ](xref:microsoft.quantum.contributing.api-design). Los programas y bibliotecas de Q# que se compilan sin advertencias en la versión 0.11.2004.2825 seguirán funcionando sin modificar.

Consulte la lista completa de solicitudes de incorporación de cambios cerradas para [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiladores](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtimes](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ejemplos](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) y [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01120042825"></a>Versión 0.11.2004.2825

*Fecha de lanzamiento: 30 de abril de 2020*

Esta versión contiene lo siguiente:

- Nueva compatibilidad con aplicaciones de línea de comandos de Q#, que ya no requieren un archivo host de C# o Python. Para más información sobre cómo empezar a usar las aplicaciones de línea de comandos de Q#, consulte [aquí](xref:microsoft.quantum.install.standalone).
- Se ha actualizado el inicio rápido del generador de números cuánticos aleatorios que no necesite un archivo host de C# o Python. Consulte el [Inicio rápido](xref:microsoft.quantum.quickstarts.qrng) actualizado.
- Mejoras del rendimiento de las imágenes de Docker IQ#

> [!NOTE]
> Actualmente no se puede llamar a aplicaciones de línea de comandos de Q# que usan el nuevo atributo [`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint) desde programas host de Python o .NET.
> Para más información, consulte las guías de [Python](xref:microsoft.quantum.install.python) y [Interoperabilidad de .NET](xref:microsoft.quantum.install.cs).

## <a name="version-01120033107"></a>Versión 0.11.2003.3107

*Fecha de lanzamiento: 31 de marzo de 2020*

Esta versión contiene correcciones menores de la versión 0.11.2003.2506.

## <a name="version-01120032506"></a>Version 0.11.2003.2506

*Fecha de lanzamiento: 26 de marzo de 2020*

Esta versión contiene lo siguiente:

- Se ha agregado compatibilidad con los modificadores de acceso en Q#. Para más información, consulte [Estructuras de archivo](xref:microsoft.quantum.guide.filestructure).
- Se ha actualizado al SDK de .NET Core 3.1.

Consulte la lista completa de solicitudes de incorporación de cambios cerradas para [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiladores](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [tiempo de ejecución](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ejemplos](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) y [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020022610"></a>Versión 0.10.2002.2610

*Fecha de lanzamiento: 27 de febrero de 2020*

Esta versión contiene lo siguiente:

- Nueva biblioteca de aprendizaje automático cuántico. Para más información, visite nuestra [página de documentación sobre QML](https://docs.microsoft.com/quantum/libraries/machine-learning/?view=qsharp-preview).
- Correcciones de errores de IQ#, que dan como resultado un aumento del rendimiento de 10 a 20 veces superior al cargar paquetes NuGet.

Consulte la lista completa de solicitudes de incorporación de cambios cerradas para [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiladores](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [tiempo de ejecución](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ejemplos](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) y [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020012831"></a>Versión 0.10.2001.2831

*Fecha de lanzamiento: 29 de enero de 2020*

Esta versión contiene lo siguiente:

- Nuevo paquete NuGet Microsoft.Quantum.SDK, que reemplazará al paquete NuGet Microsoft.Quantum.Development.Kit al crear nuevos proyectos. El paquete NuGet Microsoft.Quantum.Development.Kit se seguirá admitiendo en los proyectos existentes. 
- Compatibilidad con las extensiones de compilador de Q#, habilitadas por el nuevo paquete NuGet Microsoft.Quantum.SDK. Para más información, consulte la [documentación en GitHub](https://github.com/microsoft/qsharp-compiler/tree/master/src/QuantumSdk#extending-the-q-compiler), el [ejemplo de extensiones de compilador](https://github.com/microsoft/qsharp-compiler/tree/master/examples/CompilerExtensions) y el [blog para desarrolladores de Q#](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/).
- Se ha agregado compatibilidad con .NET Core 3.1. Se recomienda encarecidamente tener instalada la versión 3.1.100, ya que la compilación con versiones anteriores del SDK de .NET Core puede causar problemas
- Nuevas transformaciones del compilador disponibles en Microsoft.Quantum.QsCompiler.Experimental
- Nueva funcionalidad para exponer vectores de estado de salida como HTML en IQ#
- Se ha agregado compatibilidad de EstimateFrequencyA con Microsoft.Quantum.Characterization para las pruebas de Hadamard y SWAP
- El espacio de nombres AmplitudeAmplification ahora usa la guía de estilo de Q#

Consulte la lista completa de solicitudes de incorporación de cambios cerradas para [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiladores](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [tiempo de ejecución](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ejemplos](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) y [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019120501"></a>Versión 0.10.1912.0501

*Fecha de lanzamiento: 5 de diciembre de 2019*

Esta versión contiene lo siguiente:

- Nuevo atributo de prueba para las pruebas unitarias de Q#. Consulte la documentación de API actualizada [aquí](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test) y la guía de prueba y depuración actualizada [aquí](xref:microsoft.quantum.guide.testingdebugging)
- Se ha agregado un seguimiento de la pila en caso de un error de ejecución de un programa en Q#
- Se ha incorporado la compatibilidad con puntos de interrupción en Visual Studio Code debido a una actualización de la [extensión de Visual Studio Code en C# para OmniSharp](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)

Consulte la lista completa de solicitudes de incorporación de cambios cerradas para [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiladores](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [tiempo de ejecución](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ejemplos](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) y [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019111607"></a>Versión 0.10.1911.1607

*Fecha de lanzamiento: 17 de noviembre de 2019*

Esta versión contiene lo siguiente:

- Corrección del rendimiento de [Quantum Katas](https://github.com/Microsoft/QuantumKatas) y cuadernos de Jupyter Notebook

Consulte la lista completa de solicitudes de incorporación de cambios cerradas para [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiladores](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [tiempo de ejecución](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ejemplos](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) y [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  


## <a name="version-0101911307"></a>Versión 0.10.1911.307

*Fecha de lanzamiento: 1 de noviembre de 2019*

Esta versión contiene lo siguiente:

- Actualizaciones para las extensiones de Visual Studio Code y Visual Studio para implementar un servidor de lenguaje como un archivo ejecutable independiente, eliminando la dependencia en la versión del SDK de .NET Core  
- Migración a .NET Core 3.0
- Cambio importante en Microsoft.Quantum.Simulation.Core.IOperationFactory con presentación del nuevo método `Fail`. Solo afecta a los simuladores personalizados que no extienden SimulatorBase. Para más información, [vea la solicitud de incorporación de cambios de GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).
- Nuevo soporte para atributos en desuso

Consulte la lista completa de solicitudes de incorporación de cambios cerradas para [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiladores](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [tiempo de ejecución](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ejemplos](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) y [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0919093002"></a>Versión 0.9.1909.3002

*Fecha de lanzamiento: 30 de septiembre de 2019*

Esta versión contiene lo siguiente:

- Nueva compatibilidad para finalización de código Q# en Visual Studio 2019 (versiones 16.3 y posteriores) y Visual Studio Code.
- Nueva [Quantum Kata](https://github.com/Microsoft/QuantumKatas) para agregadores cuánticos.

Consulte la lista completa de solicitudes de incorporación de cambios cerradas para [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiladores](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [tiempo de ejecución](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ejemplos](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) y [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-09-packagereference-0919082902"></a>Versión 0.9 (*PackageReference 0.9.1908.2902*)

*Fecha de lanzamiento: 29 de agosto de 2019*

Esta versión contiene lo siguiente:

- Nueva compatibilidad con [instrucciones de conjugación](xref:microsoft.quantum.guide.operationsfunctions#conjugations) en Q#.
- Nuevas acciones de código en el compilador, como: "reemplazar por", "agregar documentación" y actualización de elementos de matriz simples.
- Se ha agregado una plantilla de instalación y nuevos comandos de proyecto a la extensión de Visual Studio Code.
- Se han agregado nuevas variantes del combinador ApplyIf, como [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone).
- [Quantum Katas](https://github.com/Microsoft/QuantumKatas) adicionales convertidas a Jupyter Notebooks.
- La extensión de Visual Studio ahora requiere Visual Studio 2019.

Consulte la lista completa de solicitudes de incorporación de cambios cerradas para [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiladores](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [tiempo de ejecución](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ejemplos](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) y [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

Aquí se resumen los cambios, así como las instrucciones para actualizar los programas existentes.  Obtenga más información sobre estos cambios en el [blog para desarrolladores de Q#](https://devblogs.microsoft.com/qsharp).

## <a name="version-08-packagereference-0819071701"></a>Versión 0.8 (*PackageReference 0.8.1907.1701*)

*Fecha de lanzamiento: 12 de julio de 2019*

Esta versión contiene lo siguiente:

- Nuevas ubicaciones de indexación para la segmentación de matrices; [consulte la referencia de lenguaje](xref:microsoft.quantum.guide.expressions#array-slices) para más información.
- Se ha agregado Dockerfile hospedado en [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry); consulte el [repositorio de IQ# para más información](https://github.com/microsoft/iqsharp/blob/master/README.md).
- Cambio importante en [el simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro), actualización de los valores de configuración, cambios en los nombres; consulte el Explorador de API [.NET para ver los nombres actualizados](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).

Consulte la lista completa de solicitudes de incorporación de cambios cerradas para [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) y [ejemplos](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-07-packagereference-0719053109"></a>Versión 0.7 (*PackageReference 0.7.1905.3109*)

*Fecha de lanzamiento: 31 de mayo de 2019*

Esta versión contiene lo siguiente:
- Adiciones al lenguaje de Q#. 
- Actualizaciones de la biblioteca de química. 
- Una nueva biblioteca de valores numéricos.

Consulte la lista completa de solicitudes de incorporación de cambios cerradas para [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) y [ejemplos](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Aquí se resumen los cambios, así como las instrucciones para actualizar los programas existentes.  Obtenga más información sobre estos cambios en el [blog para desarrolladores de Q#](https://devblogs.microsoft.com/qsharp).

### <a name="q-language-syntax"></a>Sintaxis del lenguaje Q#
Esta versión agrega una nueva sintaxis del lenguaje Q#:
* Se han agregado elementos con nombre para [tipos definidos por el usuario](xref:microsoft.quantum.guide.types#user-defined-types).  
* Los constructores de tipos definidos por el usuario ahora se pueden usar como funciones.
* Se ha agregado compatibilidad con [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) y [apply-and-reassign](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) en tipos definidos por el usuario.
* El bloque de corrección para bucles [repeat-until-success](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) ahora es opcional.
* Ahora se admiten bucles while en funciones (no en operaciones).

### <a name="library"></a>Biblioteca 

En esta versión se agrega una biblioteca de valores numéricos: Obtenga más información sobre cómo [usar la nueva biblioteca de valores numéricos](xref:microsoft.quantum.numerics.usage) y probar los [nuevos ejemplos](https://github.com/microsoft/quantum/tree/master/Numerics).  [PR 102](https://github.com/Microsoft/QuantumLibraries/pull/102).  

Esta versión reorganiza, extiende y actualiza la biblioteca de química:
* Mejora la modularidad de los componentes, la extensibilidad y la limpieza de código general.  [PR #58](https://github.com/microsoft/QuantumLibraries/pull/58).
* Se agrega compatibilidad para [funciones de onda de varias referencias](xref:microsoft.quantum.chemistry.concepts.multireference), tanto funciones de onda de varias referencias dispersas como un clúster acoplado unitario.  [PR 110](https://github.com/Microsoft/QuantumLibraries/pull/110).
* (Gracias) Colaborador de [1QBit](https://1qbit.com) ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): evaluación de energía con ansatz variacional. [PR 120](https://github.com/Microsoft/QuantumLibraries/pull/120).
* Actualización del esquema de [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) a la nueva [versión 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2); adición de especificación de clúster acoplado unitario. [Problema 65](https://github.com/microsoft/QuantumLibraries/issues/65).
* Adición de interoperabilidad de Python a las funciones de la biblioteca de química. Pruebe este [ejemplo](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration). [Incidencia 53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR 110](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>Versión 0.6.1905

*Fecha de lanzamiento: 3 de mayo de 2019*

Esta versión contiene lo siguiente:
- Realiza cambios en el lenguaje Q#. 
- Reestructura las bibliotecas de Quantum Development Kit. 
- Agrega nuevos ejemplos. 
- Corrige errores.  Consulte las solicitudes de incorporación de cambios cerradas para [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) y [ejemplos](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Aquí se resumen los cambios, así como las instrucciones para actualizar los programas existentes.  Puede obtener más información sobre estos cambios en devblogs.microsoft.com/qsharp.

### <a name="q-language-syntax"></a>Sintaxis del lenguaje Q#
Esta versión agrega una nueva sintaxis del lenguaje Q#:
* Agregue una [forma abreviada de expresar las especializaciones de las operaciones cuánticas](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations) (control y adjuntos) con operadores `+`.  La sintaxis antigua está en desuso.  Los programas que usan la sintaxis antigua (por ejemplo, `: adjoint`) seguirán funcionando, pero se generará una advertencia de tiempo de compilación.  
* Agregue un nuevo operador para [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions), `w/`, que se puede usar para expresar la creación de la matriz como una modificación de una matriz existente.
* Agregue la [instrucción apply-and-update](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) común, por ejemplo, `+=`, `w/=`.
* Agregue una manera de especificar un nombre corto para los espacios de nombres en [directivas Open](xref:microsoft.quantum.guide.filestructure#open-directives).

Con esta versión, ya no se permite especificar un elemento de matriz en el lado izquierdo de una instrucción set.  Esto se debe a que esa sintaxis implica que las matrices son mutables cuando, de hecho, el resultado de la operación siempre ha sido la creación de una nueva matriz con la modificación.  En su lugar, se generará un error del compilador con una sugerencia para usar el nuevo operador de copia y actualización, `w/`, para lograr el mismo resultado.  

### <a name="library-restructuring"></a>Reestructuración de la biblioteca
Esta versión reorganiza las bibliotecas para permitir que crezcan de manera coherente:
* Cambia el nombre del espacio de nombres Microsoft.Quantum.Primitive a Microsoft.Quantum.Intrinsic.  Estas operaciones las implementa la máquina de destino.  El espacio de nombres Microsoft.Quantum.Primitive está en desuso.  Una advertencia en tiempo de ejecución le avisará cuando los programas llamen a operaciones y funciones mediante nombres en desuso.

* Cambia el nombre del paquete Microsoft.Quantum.Canon a Microsoft.Quantum.Standard.  Este paquete contiene espacios de nombres que son comunes a la mayoría de los programas de Q#.  Esto incluye:  
    - Microsoft.Quantum.Canon para operaciones comunes
    - Microsoft.Quantum.Arithmetic para operaciones aritméticas de uso general
    - Microsoft.Quantum.Preparation para operaciones usadas para preparar el estado de qubit
    - Microsoft.Quantum.Simulation para funcionalidades de simulación

Con este cambio, los programas que incluyen una única instrucción "Open" para el espacio de nombres Microsoft.Quatum.Canon pueden encontrar errores de compilación si el programa hace referencia a operaciones que se han movido a los otros tres espacios de nombres nuevos.  La adición de instrucciones Open adicionales para los tres nuevos espacios de nombres es una forma sencilla de resolver este problema.  

* Varios espacios de nombres están en desuso, ya que sus operaciones se han reorganizado en otros espacios de nombres. Los programas que usan estos espacios de nombres seguirán funcionando y una advertencia de tiempo de compilación indicará el espacio de nombres donde se define la operación.  

* El espacio de nombres Microsoft.Quantum.Arithmetic se ha normalizado para que use el tipo definido por el usuario <xref:microsoft.quantum.arithmetic.littleendian>. Utilice la función [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian) cuando sea necesario para realizar la conversión a little endian.  

* Los nombres de varias funciones y operaciones invocables se han cambiado para que se ajusten a la [guía de estilo de Q#](xref:microsoft.quantum.contributing.style).  Los nombres invocables anteriores están en desuso.  Los programas que usan los nombres invocables anteriores seguirán funcionando con una advertencia en tiempo de compilación. 

### <a name="new-samples"></a>Nuevos ejemplos

Hemos agregado un [ejemplo de uso de Q# con un controlador de F#](https://github.com/Microsoft/Quantum/pull/164).  

**Gracias** al siguiente colaborador de nuestra base de código abierto en http://github.com/Microsoft/Quantum. Estas contribuciones son una importante aportación a los ejemplos de código Q#:

* Mathias Soeken ([@msoeken](https://github.com/msoeken)): Síntesis de las funciones de caja negra. [PR #135](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Migración de proyectos existentes a la versión 0.6.1905.

Consulte la [guía de instalación](xref:microsoft.quantum.install) para actualizar QDK.
  
Si ya tiene proyectos de Q# de la versión 0.5 de Quantum Development Kit, estos son los pasos para migrar los proyectos a la versión más reciente.

    1. Los proyectos deben actualizarse en orden.  Si tiene una solución con varios proyectos, actualice cada proyecto en el orden en el que se hace referencia a ellos.
    2. En una línea de comandos, ejecute `dotnet clean` para quitar todos los archivos binarios y los archivos intermedios existentes.
    3. En un editor de texto, edite el archivo .csproj para cambiar la versión de todos los `PackageReference` "Microsoft.Quantum" a la versión 0.6.1904, y cambie el nombre del paquete "Microsoft.Quantum.Canon" por "Microsoft.Quantum.Standard"; por ejemplo:

         ```xml
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
        ```
    4. En la línea de comandos, ejecute este comando: `dotnet msbuild`  
    5. Después de ejecutarlo, es posible que tenga que solucionar los errores manualmente debido a los cambios mencionados anteriormente.  En muchos casos, los errores también se mostrarán mediante IntelliSense en Visual Studio o Visual Studio Code.
        - Abra la carpeta raíz del proyecto o la solución que lo contiene en Visual Studio 2019 o Visual Studio Code.
        - Después de abrir un archivo .qs en el editor, verá el resultado de la extensión del lenguaje Q# en la ventana de salida.
        - Una vez que el proyecto se ha cargado correctamente (loq ue se indica en la ventana de salida), abra cada archivo y solucione manualmente todos los problemas que queden.

> [!NOTE]
> * En la versión 0.6, el servidor de lenguaje incluido en Quantum Development Kit no admite varias áreas de trabajo.
> * Para trabajar con un proyecto en Visual Studio Code, abra la carpeta raíz que contiene el proyecto y todos los proyectos a los que se hace referencia.   
> * Para trabajar con una solución en Visual Studio, todos los proyectos contenidos en la solución deben estar en la misma carpeta que la solución o en una de sus subcarpetas.  
> * **No** se admiten referencias entre los proyectos migrados a la versión 0.6 y los proyectos que usan paquetes de versiones anteriores.

## <a name="version-051904"></a>Versión 0.5.1904

*Fecha de lanzamiento: 15 de abril de 2019*

Esta versión contiene correcciones de errores.


## <a name="version-051903"></a>Versión 0.5.1903

*Fecha de lanzamiento: 27 de marzo de 2019*

Esta versión contiene lo siguiente:

- Agrega compatibilidad con Jupyter Notebook, que ofrece una excelente manera de obtener información sobre Q#.  [Consulte los nuevos ejemplos de Jupyter Notebook y aprenda a escribir sus propios cuadernos](xref:microsoft.quantum.install). 

- Agrega la aritmética del agregador de enteros a la biblioteca Quantum Canon.  Vea también un cuaderno de Jupyter Notebook que [describe cómo usar los nuevos agregadores de enteros](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb).

- Corrección de errores para el problema de DumpRegister notificado por la comunidad ([#148](https://github.com/Microsoft/Quantum/issues/148)).

- Se ha agregado la capacidad para volver desde dentro de una [instrucción using](xref:microsoft.quantum.guide.qubits#allocating-qubits).

- Se ha renovado la [guía de introducción](xref:microsoft.quantum.install).


## <a name="version-051902"></a>Versión 0.5.1902

*Fecha de lanzamiento: 27 de febrero de 2019*

Esta versión contiene lo siguiente:

- Agrega compatibilidad para un host de Python multiplataforma.  El paquete `qsharp` de Python facilita la simulación de operaciones y funciones de Q# desde Python. Más información acerca de la [interoperabilidad de Python](xref:microsoft.quantum.install). 

- Las extensiones de Visual Studio y Visual Studio Code ahora admiten el cambio de nombre de los símbolos (por ejemplo, funciones y operaciones).

- La extensión de Visual Studio ahora se puede instalar en Visual Studio 2019.

## <a name="version-041901"></a>Versión 0.4.1901

*Fecha de lanzamiento: 30 de enero de 2019*

Esta versión contiene lo siguiente:

- Agrega compatibilidad para un nuevo tipo primitivo, BigInt, que representa un entero con signo de tamaño arbitrario.  Obtenga más información sobre el [tipo BigInt](xref:microsoft.quantum.guide.types).
- Agrega un nuevo simulador de Toffoli, un simulador rápido con una finalidad especial, que puede simular operaciones X, CNOT y operaciones cuánticas X multicontrol con un gran número de qubits.  Obtenga más información sobre el [simulador de Toffoli](xref:microsoft.quantum.machines.toffoli-simulator).
- Agrega una calculadora de recursos simple que calcula los recursos necesarios para ejecutar una instancia determinada de una operación de Q# en un equipo cuántico.  Más información sobre la [calculadora de recursos](xref:microsoft.quantum.machines.resources-estimator).


## <a name="version-0318112802"></a>Versión 0.3.1811.2802

*Fecha de lanzamiento: 28 de noviembre de 2018*

Aunque nuestra extensión de VS Code no lo estaba usando, se marcó y se quitó de Marketplace durante la [purga de extensiones](https://code.visualstudio.com/blogs/2018/11/26/event-stream) relacionadas con el paquete `event-stream` de NPM. Esta versión quita todas las dependencias en tiempo de ejecución que podrían hacer que la extensión desencadene banderas rojas.

Si ya había instalado la extensión, tendrá que instalarla de nuevo. Para ello, busque [Microsoft Quantum Development Kit for Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) en Visual Studio Marketplace y presione Instalar. Lamentamos las molestias.


## <a name="version-0318111511"></a>Versión 0.3.1811.1511

*Fecha de lanzamiento: 20 de noviembre de 2018*

En esta versión se corrige un error que impedía a algunos usuarios cargar correctamente la extensión de Visual Studio.

Si va a actualizar desde la versión 0.2 de Quantum Development Kit, obtenga más información sobre los [cambios en el lenguaje Q# y la migración de su programa de Q#](xref:microsoft.quantum.relnotes.migration-0-3).

## <a name="version-031811203"></a>Versión 0.3.1811.203

*Fecha de lanzamiento: 2 de noviembre de 2018*

Esta versión incluye algunas correcciones de errores, entre las que se incluyen:

* Invocar a `DumpMachine` podría cambiar el estado del simulador en determinadas situaciones.
* Se han quitado las advertencias al compilar proyectos con una versión de .NET Core anterior a 2.1.403.
* Se ha limpiado la documentación, especialmente la información sobre herramientas que se muestra al mantener el mouse en VS Code o Visual Studio.

Si va a actualizar desde la versión 0.2 de Quantum Development Kit, obtenga más información sobre los [cambios en el lenguaje Q# y la migración de su programa de Q#](xref:microsoft.quantum.relnotes.migration-0-3).

## <a name="version-0318102508"></a>Versión 0.3.1810.2508

*Fecha de lanzamiento: 29 de octubre de 2018*

Esta versión incluye nuevas características de lenguaje y una experiencia de desarrollo mejorada:

* Esta versión incluye un servidor de lenguaje para Q# e integraciones de cliente para Visual Studio y Visual Studio Code. Esto habilita un nuevo conjunto de características de IntelliSense, además del subrayado ondulado de errores y advertencias para ver los comentarios en directo. 
* Esta actualización mejora mucho los mensajes de diagnóstico en general, con una navegación sencilla e intervalos precisos para el diagnóstico, así como detalles adicionales en la información que se muestra al mantener el mouse encima.
* El lenguaje Q# se ha ampliado para unificar las formas en que los desarrolladores pueden realizar operaciones comunes, y se han mejorado las características del lenguaje para expresar la computación cuántica de forma eficaz.  En esta versión se han realizado algunos cambios importantes en el lenguaje Q#.   

Obtenga más información sobre los cambios en el [lenguaje Q# y la migración de su programa de Q#](xref:microsoft.quantum.relnotes.migration-0-3).

Esta versión también incluye una nueva biblioteca de química cuántica:

* La biblioteca de química contiene nuevas características de simulación de funciones de Hamilton, entre las que se incluyen:
    - Integradores de Trotter-Suzuki de orden par arbitrario para mejorar la precisión de la simulación.
    - Técnica de simulación de qubitización con optimizaciones específicas para química para reducir la complejidad de las puertas $T$.
* Se ha incorporado un nuevo esquema de código abierto, llamado esquema de Broombridge (en referencia al [lugar](https://en.wikipedia.org/wiki/Broom_Bridge) donde se celebra el nacimiento de las funciones de Hamilton), para importar representaciones de moléculas y simularlas.
* Se proporcionan varias representaciones químicas definidas mediante el esquema de Broombridge.  Estos modelos se generaron con [NWChem](http://www.nwchem-sw.org/), una herramienta de química computacional de alto rendimiento y código abierto.
* En los tutoriales y los ejemplos se describe cómo usar la biblioteca de química y los modelos de datos de Broombridge para:
    - Construir funciones de Hamilton simples mediante la biblioteca de química.
    - Visualizar las energías del hidruro de litio en reposo y excitado mediante estimación de la fase.
    - Realizar estimaciones de los recursos para la simulación química cuántica.
    - Calcular los niveles de energía de las moléculas representadas por el esquema de Broombridge.
* En la documentación se describe cómo usar NWChem para generar modelos químicos adicionales para la simulación cuántica con Q#.

Obtenga más información sobre la [biblioteca de química de Quantum Development Kit](xref:microsoft.quantum.chemistry.concepts.intro).

Con la nueva biblioteca de química, hemos separando las bibliotecas en un nuevo repositorio de GitHub, [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).  Los ejemplos permanecen en el repositorio [Microsoft/Quantum](https://github.com/Microsoft/Quantum).  Le agradecemos las contribuciones a ambos.

Esta versión incluye correcciones de errores y características para los problemas notificados por la comunidad:

* ¿Intellisense para Q#? ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).
* Archivos .qs ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).
* Se ha mejorado el mensaje de error si las llaves se abrevian en la instrucción if ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).
* Compatibilidad con la desconstrucción de tuplas en un (re)enlace mutable ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).
* Error al ejecutar el BitFlipCode proporcionado ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).
* H2SimulationGUI muestra grandes picos a veces ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).

### <a name="community-contributions"></a>Contribuciones de la comunidad

**Gracias** a las siguientes personas que han contribuido a nuestra base de código abierto en http://github.com/Microsoft/Quantum. Estas contribuciones son una importante aportación a los ejemplos de código Q#:

* Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)): Se ha mejorado la experiencia de los desarrolladores de QASM/Q# mediante la creación de un QASM al traductor de Q#. [PR #58](https://github.com/Microsoft/Quantum/pull/58).

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  Ha aportado un ejemplo de implementación del juego CHSH, un juego cuántico relacionado con la no localizabilidad.  [PR #84](https://github.com/Microsoft/Quantum/pull/84).

Gracias también Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR #90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) y Lee James O'Riordan ([@mlxd](https://github.com/mlxd),[#96](https://github.com/Microsoft/Quantum/pull/96)) por su trabajo de mejora del contenido de la documentación y las correcciones ortográficas. 

## <a name="version-021809701"></a>Versión 0.2.1809.701

*Fecha de lanzamiento: 10 de septiembre de 2018*

Esta versión incluye correcciones de errores para los problemas notificados por la comunidad. Incluye:

* No se puede usar el operador de desplazamiento ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).
* `DumpMachine` / `DumpRegister` produce un error en `QCTraceSimulator` al imprimir en la consola ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).
* Permitir la asignación de 0 qubits ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).
* `AssertQubitState` requiere una llamada Complex() explícita ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).
* La operación `Measure` siempre devuelve `One` en macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).

Gracias. 

## <a name="version-0218063001"></a>Versión 0.2.1806.3001

*Fecha de lanzamiento: 30 de junio de 2018*

Esta versión es solo una corrección rápida del [problema 48 que se muestra en GitHub](https://github.com/Microsoft/Quantum/issues/48) (se produce un error de compilación de Q# si el nombre de usuario contiene un espacio en blanco). Siga las mismas instrucciones de actualización que para `0.2.1806.1503` con la nueva versión correspondiente (`0.2.1806.3001-preview`).

## <a name="version-0218061503"></a>Versión 0.2.1806.1503

*Fecha de lanzamiento: 22 de junio de 2018*

Esta versión incluye varias contribuciones de la comunidad, así como una experiencia de depuración mejorada y mejor rendimiento.  Concretamente:

* Mejoras de rendimiento en simulaciones pequeñas y grandes para el equipo de destino de QuantumSimulator.
* Funcionalidad de depuración mejorada.
* Contribuciones de la comunidad en correcciones de errores, nuevas funciones auxiliares, operaciones y nuevos ejemplos.

### <a name="performance-improvements"></a>Mejoras en el rendimiento

Esta actualización incluye importantes mejoras de rendimiento para la simulación de números grandes y pequeños de qubits para todas las máquinas de destino.  Esta mejora se ve fácilmente con la simulación de H<sub>2</sub>, que es un ejemplo estándar de Quantum Development Kit.

### <a name="improved-debugging-functionality"></a>Funcionalidad de depuración mejorada

Esta actualización agrega nueva funcionalidad de depuración:
* Se han agregado dos nuevas operaciones, @"microsoft.quantum.extensions.diagnostics.dumpmachine" y @"microsoft.quantum.extensions.diagnostics.dumpregister", que generan información sobre la función Wave relativa a la máquina cuántica de destino en un momento dado.  
* En Visual Studio, la probabilidad de medir un $\ket{1}$ en un único qubit ahora se muestra automáticamente en la ventana de depuración para la máquina de destino de QuantumSimulator.
* En Visual Studio, se ha mejorado la visualización de las propiedades de las variables en las ventanas de depuración **Autos** y **Locals**. 

Más información acerca de las [pruebas y depuración](xref:microsoft.quantum.guide.testingdebugging).

### <a name="community-contributions"></a>Contribuciones de la comunidad

La comunidad de programadores de Q# está creciendo y estamos encantados de ver que los usuarios han aportado los primeros ejemplos y bibliotecas a nuestra base de código abierto en http://github.com/Microsoft/quantum.  **Muchísimas gracias** a los colaboradores siguientes:
* Mathias Soeken ([@msoeken](https://github.com/msoeken)): ha aportado un ejemplo que define un método de síntesis lógica basado en una transformación, que construye redes Toffoli para implementar una permutación determinada. El código está escrito completamente con funciones y operaciones de Q#.  [PR #41](https://github.com/Microsoft/Quantum/pull/41).
* RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman)): Rolf Huisman, Microsoft MVP, ha aportado un ejemplo que genera código QASM plano a partir de código de Q# para una clase restringida de programas que no tienen un flujo de control clásico y que tienen operaciones cuánticas restringidas. [PR #59](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): ha ayudado a mejorar nuestra base de código mediante el envío de una función de biblioteca para operaciones controladas. [PR #53](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): ha corregido @"microsoft.quantum.canon.quantumphaseestimation" y ha creado nuevas pruebas unitarias.  [PR #54](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): ha limpiado el ejemplo de teleportabilidad y se ha asegurado de que se desecha la instancia de QuantumSimulator. [PR #20](https://github.com/Microsoft/Quantum/pull/20)

Además, **muchas gracias** a estos ingenieros de software de Microsoft, de los equipos de servicios de ingeniería comercial, que hicieron cambios importantes en nuestra documentación durante su hackathon.  Sus cambios han mejorado considerablemente la claridad y la experiencia de incorporación para todos:
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>Actualización de los proyectos existentes

Esta versión es totalmente compatible con versiones anteriores. Solo tiene que actualizar los paquetes NuGet de los proyectos a la versión `0.2.1806.1503-preview` y realizar una **recompilación completa** para asegurarse de que se vuelven a generar todos los archivos intermedios.

En Visual Studio, siga las instrucciones habituales sobre cómo [actualizar un paquete](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).

Para actualizar las plantillas de proyecto para la línea de comandos, ejecute el siguiente comando:
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

Después de ejecutar este comando, todos los proyectos nuevos creados con `dotnet new <project-type> -lang Q#` usarán automáticamente esta versión de Quantum Development Kit.

Para actualizar un proyecto existente para que use la versión más reciente, ejecute el siguiente comando desde el directorio de cada proyecto:

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

Si un proyecto existente también usa la integración de XUnit para las pruebas unitarias, se puede usar un comando similar para actualizar el paquete:
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

En función de la versión de XUnit que use el proyecto de prueba, puede que también tenga que actualizar XUnit a la versión 2.3.1:
```
dotnet add package xunit -v "2.3.1" 
```

Después de la actualización, asegúrese de quitar todos los archivos temporales generados por la versión anterior; para ello, haga lo siguiente:
```
dotnet clean 
```

### <a name="known-issues"></a>Problemas conocidos

No hay problemas conocidos adicionales para notificar.


## <a name="version-0218022202"></a>Versión 0.2.1802.2202

*Fecha de lanzamiento: 26 de febrero de 2018*

Esta versión ofrece compatibilidad para el desarrollo en más plataformas, interoperabilidad de lenguajes y mejoras de rendimiento. Concretamente:

- Compatibilidad con el desarrollo para macOS y Linux. 
- Compatibilidad con .NET Core, incluida la compatibilidad con Visual Studio Code multiplataforma.
- Una licencia de código abierto completa para las bibliotecas de Quantum Development Kit.
- Mejora del rendimiento del simulador en proyectos que requieren 20 o más qubits.
- Interoperabilidad con el lenguaje Python (versión preliminar disponible en Windows).

### <a name="net-editions"></a>Ediciones de .NET

La plataforma .NET está disponible en dos ediciones diferentes, .NET Framework, que se proporciona con Windows, y .NET Core de código abierto, que está disponible en Windows, macOS y Linux.
Con esta versión, la mayoría de las partes de Quantum Development Kit se proporcionan como bibliotecas para .NET Standard, el conjunto de clases comunes a las ediciones Framework y Core.
Por lo tanto, estas bibliotecas son compatibles con las versiones recientes de .NET Framework o .NET Core.

De este modo, para ayudar a garantizar la máxima portabilidad de los proyectos escritos con Quantum Development Kit, se recomienda que los proyectos de biblioteca escritos con Quantum Development Kit tengan .NET Standard como destino, y que las aplicaciones de consola tengan .NET Core como destino.
Dado que las versiones anteriores de Quantum Development Kit solo admitían .NET Framework, es posible que tenga que migrar los proyectos existentes. Consulte a continuación más información sobre cómo hacerlo.

### <a name="project-migration"></a>Migración de proyectos

Los proyectos creados con versiones anteriores de Quantum Development Kit seguirán funcionando, siempre y cuando no se actualicen los paquetes NuGet que se usan en ellos. Para migrar el código existente a la nueva versión, siga estos pasos:
1. Cree un nuevo proyecto de .NET Core con el tipo correcto de plantilla de proyecto de Q# (aplicación, biblioteca o proyecto de prueba).
2. Copie los archivos .qs y .cs/.fs existentes del proyecto antiguo al nuevo proyecto mediante Add > Existing Item (Agregar > Elemento existente). No copie el archivo AssemblyInfo.cs.
3. Compile y ejecute el nuevo proyecto.

Tenga en cuenta que la operación RandomWalkPhaseEstimation del espacio de nombres Microsoft.Quantum.Canon se ha trasladado al espacio de nombres Microsoft.Research.Quantum.RandomWalkPhaseEstimation del repositorio [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc).

### <a name="known-issues"></a>Problemas conocidos

- La opción `--filter` para `dotnet test` no funciona correctamente para las pruebas escritas en Q#.
  Como resultado, no se pueden ejecutar pruebas unitarias individuales en Visual Studio Code. Se recomienda usar `dotnet test` en la línea de comandos para volver a ejecutar todas las pruebas.

## <a name="version-0118011707"></a>Versión 0.1.1801.1707

*Fecha de lanzamiento: 18 de enero de 2018*

En esta versión se corrigen algunos problemas notificados por la comunidad. Concretamente:

- El simulador funciona ahora con CPU sin AVX antiguas.
- La configuración decimal regional no provocará un error del analizador de Q#.
- La operación primitiva `SignD` ahora devuelve `Int` en lugar de `Double`.


## <a name="version-011712901"></a>Versión 0.1.1712.901

*Fecha de lanzamiento: 11 de diciembre de 2017*

### <a name="known-issues"></a>Problemas conocidos

#### <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

- El simulador incluido en Quantum Development Kit requiere una instalación de 64 bits de Microsoft Windows para ejecutarse.
- El simulador cuántico de Microsoft, que se instala con Quantum Development Kit, emplea extensiones vectoriales avanzadas (AVX) y requiere una CPU compatible con AVX. Los procesadores Intel incluidos en primer trimestre de 2011 (Sandy Bridge), o posteriores, son compatibles con AVX. Estamos evaluando la compatibilidad con CPU anteriores y podrían anunciarse detalles más adelante.

#### <a name="project-creation"></a>Creación de proyectos

- Al crear una solución (.sln) que usará Q#, la solución debe ser un directorio superior a cada proyecto (.csproj) de la solución. Al crear una nueva solución, esto se puede lograr asegurándose de que la casilla Crear directorio para la solución del cuadro de diálogo Nuevo proyecto está activada. Si no es así, los paquetes NuGet de Quantum Development Kit deberán instalarse manualmente.

#### <a name="q"></a>Q#

- IntelliSense no muestra los errores correctos del código Q#. Asegúrese de mostrar los errores de compilación en la lista de errores de Visual Studio para ver los errores de Q# correctos. Asimismo, tenga en cuenta que los errores de Q# no aparecerán hasta que se haya realizado una compilación.
- El uso de una matriz mutable en una aplicación parcial puede provocar un comportamiento inesperado.
- El enlace de una matriz inmutable a una matriz mutable (sea a = b, donde b es una matriz mutable) puede provocar un comportamiento inesperado.
- La generación de perfiles, la cobertura de código y otros complementos de VS no siempre cuentan con precisión las líneas y bloques de Q#.
- El compilador de Q# no valida cadenas interpoladas. Es posible crear errores de compilación de C# escribiendo incorrectamente nombres de variable o usando expresiones en las cadenas interpoladas de Q#.

#### <a name="simulation"></a>Simulation

- El simulador cuántico usa OpenMP para paralelizar el álgebra lineal requerida. De forma predeterminada, OpenMP usa todos los subprocesos de hardware disponibles, lo que significa que, por lo general, los programas con un número reducido de qubits se ejecutarán lentamente, ya que la coordinación necesaria mermará el trabajo real. Esto puede corregirse si se establece la variable de entorno OMP_NUM_THREADS en un número pequeño. Como norma general, un subproceso es adecuado para un máximo de 4 qubits aproximadamente y, a partir de ahí, resulta adecuado un subproceso adicional por qubit, aunque esto depende en gran medida del algoritmo.

#### <a name="debugging"></a>Depuración

- F11 (depurar paso a paso por instrucciones) no funciona en código Q#.
- El resaltado de código en código Q# en un punto de interrupción o en una pausa de un solo paso a veces es inexacto. La línea correcta se resaltará, pero a veces el resaltado comenzará y finalizará en columnas incorrectas en la línea.

#### <a name="testing"></a>Prueba

- Las pruebas se deben ejecutar en modo de 64 bits. Si se producen errores en las pruebas con BadImageFormatException, vaya al menú Probar y seleccione Configuración de pruebas > Arquitectura del procesador predeterminada > x64.
- Algunas pruebas tardan mucho en ejecutarse (posiblemente hasta 5 minutos según la máquina). Esto es normal, ya que algunas usan más de 20 qubits. Actualmente, la prueba más grande se ejecuta con 23 qubits.

#### <a name="samples"></a>Ejemplos

- En algunas máquinas, es posible que algunas muestras pequeñas se ejecuten lentamente a menos que la variable de entorno OMP_NUM_THREADS se establezca en "1". Consulte también las notas de la versión en "Simulación".

#### <a name="libraries"></a>Bibliotecas

- Existe una suposición implícita de que los qubits que se pasan a una operación en argumentos diferentes son todos distintos. Por ejemplo, todas las operaciones de biblioteca (y todos los simuladores) suponen que los dos qubits que se pasan a una operación NOT controlada son qubits distintos. Si no se respeta esta suposición, podría producirse un comportamiento inesperado. Es posible probar esto mediante el simulador de seguimiento de equipos cuánticos.
- Es posible que la función Microsoft.Quantum.Bind no funcione como se espera en todos los casos.
- En el espacio de nombres Microsoft.Quantum.Extensions.Math, la función SignD devuelve un valor Double en lugar de un valor Int, aunque la función System.Math.Sign subyacente siempre devuelve un entero. Es seguro comparar el resultado con 1.0,-1.0 y 0.0, ya que estos valores dobles tienen representaciones binarias exactas.
