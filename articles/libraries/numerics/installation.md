---
title: 'Biblioteca de valores numéricos de Microsoft Quantum: instalación y validación'
description: Obtenga información sobre cómo agregar la biblioteca de números de quantums de Microsoft a su instalación de Visual Studio 2019 o posterior.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: cb0d00a509b3986b605dd7f15f9bccc0661bb894
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906345"
---
# <a name="numerics-library-installation-and-validation"></a>Instalación y validación de la biblioteca de valores numéricos

El kit de desarrollo de Quantum proporciona compatibilidad con la funcionalidad de los valores numéricos mediante el [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) paquete NuGet.

**> De Visual Studio = 2019:** Si usa Visual Studio 2019 o una versión posterior, puede Agregar el paquete de valores numéricos mediante el administrador de paquetes NuGet.
Para ello, seleccione "administrar paquetes NuGet..." en el elemento de menú "proyecto" de Visual Studio.

En la pestaña examinar, busque el nombre del paquete "Microsoft. Quantum. Numerics"

> [!NOTE]
> Asegúrese de marcar "incluir versión preliminar"

Se enumerarán los paquetes disponibles para su descarga.
Al mantener el mouse sobre "Microsoft. Quantum. Numerics" se revela una flecha hacia abajo a la derecha del número de versión.
Haga clic en la flecha para instalar el paquete de valores numéricos.

Para obtener más información, vea la guía de la [interfaz de usuario del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Como alternativa, puede usar la consola del administrador de paquetes para agregar la biblioteca de valores numéricos al proyecto a través de la interfaz de la línea de comandos.

![Usar la consola del administrador de paquetes desde la línea de comandos](../../media/vs2017-nuget-console-menu.png)

En la consola del administrador de paquetes, ejecute lo siguiente:

```
Install-Package Microsoft.Quantum.Numerics
```

Para obtener más información, consulte la guía de la [consola del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Línea de comandos o Visual Studio Code:** Con la línea de comandos por su cuenta o desde Visual Studio Code, puede usar el comando `dotnet` para agregar una referencia de paquete NuGet al proyecto:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>Comprobación de la instalación

Al igual que el resto del kit de desarrollo de Quantum, la biblioteca de valores numéricos incluye ejemplos que le ayudarán a empezar lo más rápido posible.
Para probar la instalación con estos ejemplos, Clone el [repositorio de ejemplos principal](https://github.com/Microsoft/Quantum) y, a continuación, ejecute uno de los ejemplos.

Para ejecutar el ejemplo [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
