---
title: Instalación y validación de la biblioteca de valores | Microsoft Docs
description: Instalación y validación de la biblioteca de valores numéricos
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: c41bb73ea484271689eea2ca1b59ce6639dc15a7
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036464"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="9699f-103">Instalación y validación de la biblioteca de valores numéricos</span><span class="sxs-lookup"><span data-stu-id="9699f-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="9699f-104">El kit de desarrollo de Quantum proporciona compatibilidad con la funcionalidad de los valores numéricos mediante el [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="9699f-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="9699f-105">**> De Visual Studio = 2019:** Si usa Visual Studio 2019 o una versión posterior, puede Agregar el paquete de valores numéricos mediante el administrador de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="9699f-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="9699f-106">Para ello, seleccione "administrar paquetes NuGet..." en el elemento de menú "proyecto" de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9699f-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="9699f-107">En la pestaña examinar, busque el nombre del paquete "Microsoft. Quantum. Numerics"</span><span class="sxs-lookup"><span data-stu-id="9699f-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="9699f-108">Asegúrese de marcar "incluir versión preliminar"</span><span class="sxs-lookup"><span data-stu-id="9699f-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="9699f-109">Se enumerarán los paquetes disponibles para su descarga.</span><span class="sxs-lookup"><span data-stu-id="9699f-109">This will list the packages available for download.</span></span>
<span data-ttu-id="9699f-110">Al mantener el mouse sobre "Microsoft. Quantum. Numerics" se revela una flecha hacia abajo a la derecha del número de versión.</span><span class="sxs-lookup"><span data-stu-id="9699f-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="9699f-111">Haga clic en la flecha para instalar el paquete de valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="9699f-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="9699f-112">Para obtener más información, vea la guía de la [interfaz de usuario del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="9699f-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="9699f-113">Como alternativa, puede usar la consola del administrador de paquetes para agregar la biblioteca de valores numéricos al proyecto a través de la interfaz de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="9699f-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![](../../media/vs2017-nuget-console-menu.png)

<span data-ttu-id="9699f-114">En la consola del administrador de paquetes, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9699f-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="9699f-115">Para obtener más información, consulte la guía de la [consola del administrador de paquetes](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="9699f-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="9699f-116">**Línea de comandos o Visual Studio Code:** Con la línea de comandos por su cuenta o desde Visual Studio Code, puede usar el comando `dotnet` para agregar una referencia de paquete NuGet al proyecto:</span><span class="sxs-lookup"><span data-stu-id="9699f-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="9699f-117">Comprobación de la instalación</span><span class="sxs-lookup"><span data-stu-id="9699f-117">Verifying your installation</span></span>

<span data-ttu-id="9699f-118">Al igual que el resto del kit de desarrollo de Quantum, la biblioteca de valores numéricos incluye ejemplos que le ayudarán a empezar lo más rápido posible.</span><span class="sxs-lookup"><span data-stu-id="9699f-118">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="9699f-119">Para probar la instalación con estos ejemplos, Clone el [repositorio de ejemplos principal](https://github.com/Microsoft/Quantum) y, a continuación, ejecute uno de los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9699f-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="9699f-120">Para ejecutar el ejemplo [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) :</span><span class="sxs-lookup"><span data-stu-id="9699f-120">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
