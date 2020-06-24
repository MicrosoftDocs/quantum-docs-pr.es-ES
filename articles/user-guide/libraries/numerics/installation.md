---
title: 'Biblioteca de valores numéricos de Microsoft Quantum: instalación y validación'
description: Obtenga información sobre cómo agregar la biblioteca de números de quantums de Microsoft a su instalación de Visual Studio 2019 o posterior.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276129"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="f72ee-103">Instalación y validación de la biblioteca de valores numéricos</span><span class="sxs-lookup"><span data-stu-id="f72ee-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="f72ee-104">El kit de desarrollo de Quantum proporciona compatibilidad con la funcionalidad de los valores numéricos mediante el [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="f72ee-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="f72ee-105">**>de Visual Studio = 2019:** Si usa Visual Studio 2019 o una versión posterior, puede Agregar el paquete de valores numéricos mediante el administrador de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="f72ee-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="f72ee-106">Para ello, seleccione "administrar paquetes NuGet..." en el elemento de menú "proyecto" de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f72ee-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="f72ee-107">En la pestaña examinar, busque el nombre del paquete "Microsoft. Quantum. Numerics"</span><span class="sxs-lookup"><span data-stu-id="f72ee-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="f72ee-108">Asegúrese de marcar "incluir versión preliminar"</span><span class="sxs-lookup"><span data-stu-id="f72ee-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="f72ee-109">Se enumerarán los paquetes disponibles para su descarga.</span><span class="sxs-lookup"><span data-stu-id="f72ee-109">This will list the packages available for download.</span></span>
<span data-ttu-id="f72ee-110">Al mantener el mouse sobre "Microsoft. Quantum. Numerics" se revela una flecha hacia abajo a la derecha del número de versión.</span><span class="sxs-lookup"><span data-stu-id="f72ee-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="f72ee-111">Haga clic en la flecha para instalar el paquete de valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="f72ee-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="f72ee-112">Para obtener más información, vea la guía de la [interfaz de usuario del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="f72ee-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="f72ee-113">Como alternativa, puede usar la consola del administrador de paquetes para agregar la biblioteca de valores numéricos al proyecto a través de la interfaz de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f72ee-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Usar la consola del administrador de paquetes desde la línea de comandos](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="f72ee-115">En la consola del administrador de paquetes, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f72ee-115">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="f72ee-116">Para obtener más información, consulte la guía de la [consola del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="f72ee-116">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="f72ee-117">**Línea de comandos o Visual Studio Code:** Con la línea de comandos por su cuenta o desde Visual Studio Code, puede usar el `dotnet` comando para agregar la referencia de paquete NuGet al proyecto:</span><span class="sxs-lookup"><span data-stu-id="f72ee-117">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="f72ee-118">Comprobación de la instalación</span><span class="sxs-lookup"><span data-stu-id="f72ee-118">Verifying your installation</span></span>

<span data-ttu-id="f72ee-119">Al igual que el resto del kit de desarrollo de Quantum, la biblioteca de valores numéricos incluye ejemplos que le ayudarán a empezar lo más rápido posible.</span><span class="sxs-lookup"><span data-stu-id="f72ee-119">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="f72ee-120">Para probar la instalación con estos ejemplos, Clone el [repositorio de ejemplos principal](https://github.com/Microsoft/Quantum) y, a continuación, ejecute uno de los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f72ee-120">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="f72ee-121">Para ejecutar el [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f72ee-121">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
