---
title: Desarrollo con Q# y Binder
description: Obtenga información sobre cómo crear una aplicación de Q# con Binder.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: quickstart
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f7e9b1ae67d6275ec7ba39ea411842dc537536c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856711"
---
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="10ceb-103">Desarrollo con Q# y Binder</span><span class="sxs-lookup"><span data-stu-id="10ceb-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="10ceb-104">Puede usar Binder para ejecutar y compartir sus cuadernos de Jupyter Notebook en línea.</span><span class="sxs-lookup"><span data-stu-id="10ceb-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="10ceb-105">Uso de Binder con los ejemplos de Microsoft QDK</span><span class="sxs-lookup"><span data-stu-id="10ceb-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="10ceb-106">Para configurar Binder automáticamente para usar los ejemplos de Microsoft QDK:</span><span class="sxs-lookup"><span data-stu-id="10ceb-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="10ceb-107">Abra un explorador y ejecute https://aka.ms/try-qsharp.</span><span class="sxs-lookup"><span data-stu-id="10ceb-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="10ceb-108">En la página de aterrizaje **Ejemplos del kit de desarrollo de Quantum**, haga clic en **cuaderno de Q#** para aprender a usar IQ# para escribir sus propios cuadernos de aplicación cuántica.</span><span class="sxs-lookup"><span data-stu-id="10ceb-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![Página de aterrizaje del QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="10ceb-110">Uso de Binder con sus propios cuadernos y repositorios</span><span class="sxs-lookup"><span data-stu-id="10ceb-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="10ceb-111">Si ya tiene cuadernos en un repositorio de GitHub, puede configurar Binder para que funcione con su repositorio:</span><span class="sxs-lookup"><span data-stu-id="10ceb-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="10ceb-112">Asegúrese de que haya un archivo llamado *Dockerfile* en el directorio raíz del repositorio.</span><span class="sxs-lookup"><span data-stu-id="10ceb-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="10ceb-113">El archivo debe contener al menos las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="10ceb-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="10ceb-114">Puede consultar cuál es la versión más reciente de IQ# en las [notas de la versión](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="10ceb-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="10ceb-115">Para más información sobre cómo crear un archivo Dockerfile, consulte la [referencia de Dockerfile](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="10ceb-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="10ceb-116">Abra un explorador en [mybinder.org](https://mybinder.org).</span><span class="sxs-lookup"><span data-stu-id="10ceb-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="10ceb-117">Escriba el nombre del repositorio como una **dirección URL de GitHub** (por ejemplo, *miNombre/miRepositorio*) y haga clic en **launch** (Iniciar).</span><span class="sxs-lookup"><span data-stu-id="10ceb-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![Formulario de MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="10ceb-119">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="10ceb-119">Next steps</span></span>

<span data-ttu-id="10ceb-120">Ahora que ha configurado el entorno de Binder, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="10ceb-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
