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
# <a name="using-additional-no-locq-libraries"></a>Uso de Q# bibliotecas adicionales

El kit de desarrollo de Quantum proporciona una funcionalidad adicional específica del dominio a través de _paquetes NuGet_ que se pueden agregar a los Q# proyectos.

| Q#Biblioteca  | Detección de | Notas |
|---------|---------|--------|
| [Q#biblioteca estándar](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft. Quantum. Standard**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | Se incluye de manera predeterminada |
| [Biblioteca de química cuántica](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [Biblioteca de valores numéricos cuánticos](xref:microsoft.quantum.numerics.intro) | [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Biblioteca de aprendizaje automático cuántico](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

Una vez que haya instalado el kit de desarrollo de Quantum para usarlo con el entorno y el lenguaje de host preferidos, puede agregar fácilmente bibliotecas a Q# proyectos individuales sin necesidad de realizar ninguna instalación adicional.

> [!NOTE]
> Algunas Q# bibliotecas pueden funcionar bien con herramientas adicionales que funcionan con sus Q# programas o que se integran con las aplicaciones host.
> Por ejemplo, las [instrucciones de instalación](xref:microsoft.quantum.chemistry.concepts.installation) de la biblioteca de química describen cómo usar el [paquete **Microsoft. Quantum. química** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) junto con la plataforma de Química computacional de NWChem y cómo instalar las `qdk-chem` herramientas de línea de comandos para trabajar con datos de química de Quantum.

## <a name="no-locq-command-line-applications-or-net-interopability"></a>[Q#aplicaciones de línea de comandos o interoperabilidad de .NET](#tab/tabid-csproj)

**Línea de comandos o Visual Studio Code:** Con la línea de comandos por su cuenta o desde Visual Studio Code, puede usar el `dotnet` comando para agregar una referencia de paquete NuGet al proyecto.
Por ejemplo, para agregar el paquete [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) , ejecute el siguiente comando:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio:** Si usa Visual Studio 2019 o una versión posterior, puede agregar paquetes adicionales Q# mediante el administrador de paquetes NuGet.
Para cargar un paquete: 
1. Con un proyecto abierto en Visual Studio, seleccione **administrar paquetes NuGet...** en el menú **proyecto** .

2. Haga clic en **examinar**, seleccione **incluir versión preliminar** y busque el nombre del paquete "Microsoft. Quantum. Numerics". Se enumerarán los paquetes disponibles para su descarga.

3. Mantenga el mouse sobre **Microsoft. Quantum. Numerics** y haga clic en la flecha hacia abajo situada a la derecha del número de versión para instalar el paquete de valores numéricos.

Para obtener más información, vea la guía de la [interfaz de usuario del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Como alternativa, puede usar la consola del administrador de paquetes para agregar la biblioteca de valores numéricos al proyecto a través de la interfaz de la línea de comandos.

![Usar la consola del administrador de paquetes desde la línea de comandos](~/media/vs2017-nuget-console-menu.png)

En la consola del administrador de paquetes, ejecute lo siguiente:

```
Install-Package Microsoft.Quantum.Numerics
```

Para obtener más información, consulte la guía de la [consola del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-console).

## <a name="ino-locq-notebooks"></a>[I Q# notebooks](#tab/tabid-notebook)

Puede hacer que los paquetes adicionales estén disponibles para su uso en un bloc de notas de I Q# mediante el [ `%package` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.package).
Por ejemplo, para agregar el paquete [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) para su uso en un Q# Bloc de notas I, ejecute el siguiente comando en una celda del cuaderno:

```
%package Microsoft.Quantum.Numerics
```

Después de este comando, el paquete está disponible para todas las celdas del Bloc de notas.
Para que el paquete esté disponible desde Q# el código en el área de trabajo actual, vuelva a cargar el área de trabajo después de agregar el paquete:

```
%workspace reload
```

## <a name="python-interoperability"></a>[Interoperabilidad de Python](#tab/tabid-python)


Puede hacer que los paquetes adicionales estén disponibles para su uso en un programa host de Python mediante el [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) método.
Por ejemplo, para agregar el paquete [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) para su uso en un Q# Bloc de notas I, ejecute el siguiente código de Python:

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

Después de este comando, el paquete estará disponible para cualquier Q# código compilado mediante `qsharp.compile` .
Para que el paquete esté disponible desde Q# el código en el área de trabajo actual, vuelva a cargar el área de trabajo después de agregar el paquete:

```python
qsharp.reload()
```

***
