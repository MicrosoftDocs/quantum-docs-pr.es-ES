---
title: Contribución de ejemplos a Microsoft QDK
description: Obtenga información sobre cómo colaborar en el Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: 20da0e1765a242c172cc595f03d7791a0e8b8d2d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867524"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="38957-103">Contribución de ejemplos al kit de desarrollo de Quantum</span><span class="sxs-lookup"><span data-stu-id="38957-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="38957-104">Si está interesado en colaborar en el código del [repositorio de ejemplos](https://github.com/Microsoft/Quantum), gracias por hacer que la comunidad Quantum Development sea un lugar mejor.</span><span class="sxs-lookup"><span data-stu-id="38957-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="38957-105">Repositorio de ejemplos del kit de desarrollo de Quantum</span><span class="sxs-lookup"><span data-stu-id="38957-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="38957-106">Para ayudarle a preparar su contribución para ayudar lo máximo posible, es útil echar un vistazo a cómo se diseña el repositorio de ejemplos:</span><span class="sxs-lookup"><span data-stu-id="38957-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

<span data-ttu-id="38957-107">Es decir, los ejemplos del [repositorio Microsoft/Quantum](https://github.com/microsoft/Quantum) se desglosan por áreas temáticas en carpetas diferentes, como `algorithms/` , `arithmetic/` o `characterization/` .</span><span class="sxs-lookup"><span data-stu-id="38957-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="38957-108">Dentro de la carpeta de cada área de asunto, cada ejemplo consta de una única carpeta que recopila todo lo que un usuario necesitará para explorar y usar ese ejemplo.</span><span class="sxs-lookup"><span data-stu-id="38957-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="38957-109">Cómo se estructuran los ejemplos</span><span class="sxs-lookup"><span data-stu-id="38957-109">How Samples are Structured</span></span>

<span data-ttu-id="38957-110">Examinando los archivos que componen cada carpeta, vamos a profundizar en el [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="38957-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="38957-111">Archivo</span><span class="sxs-lookup"><span data-stu-id="38957-111">File</span></span>              | <span data-ttu-id="38957-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="38957-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="38957-113">Q#Proyecto usado para generar el ejemplo con el SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="38957-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="38957-114">Q#operaciones y funciones para el ejemplo</span><span class="sxs-lookup"><span data-stu-id="38957-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="38957-115">Programa host de C# que se usa para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="38957-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="38957-116">Programa host de Python que se usa para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="38957-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="38957-117">Documentación sobre lo que hace el ejemplo y cómo usarlo</span><span class="sxs-lookup"><span data-stu-id="38957-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="38957-118">No todas las muestras tendrán exactamente el mismo conjunto de archivos (por ejemplo, algunos ejemplos pueden ser solo en C#, otros pueden no tener un host de Python o algunos ejemplos pueden requerir que los archivos de datos de auxiliar funcionen).</span><span class="sxs-lookup"><span data-stu-id="38957-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="38957-119">Anatomía de un archivo Léame útil</span><span class="sxs-lookup"><span data-stu-id="38957-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="38957-120">Sin embargo, un archivo especialmente importante es el `README.md` archivo, ya que es lo que los usuarios necesitan para empezar a trabajar con el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="38957-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="38957-121">Cada `README.md` una debe empezar con algunos metadatos que ayuden a docs.Microsoft.com/samples a encontrar su contribución.</span><span class="sxs-lookup"><span data-stu-id="38957-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="38957-122">Vea cómo se representa el ejemplo chsh-Game.</span><span class="sxs-lookup"><span data-stu-id="38957-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="38957-123">Estos metadatos se proporcionan como un [encabezado YAML](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) que indica qué idiomas cubre el ejemplo (normalmente, será `qsharp` , `csharp` y `python` ) y qué productos cubre el ejemplo (normalmente, solo `qdk` ).</span><span class="sxs-lookup"><span data-stu-id="38957-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="38957-124">La `page_type: sample` clave del encabezado es necesaria para que el ejemplo aparezca en docs.Microsoft.com/samples.</span><span class="sxs-lookup"><span data-stu-id="38957-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="38957-125">Del mismo modo, las `product` `language` claves y son críticas para ayudar a los usuarios a buscar y ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="38957-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="38957-126">Después, es útil proporcionar una breve introducción que indique lo que hace el nuevo ejemplo:</span><span class="sxs-lookup"><span data-stu-id="38957-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="38957-127">Los usuarios de su ejemplo también apreciarán saber lo que necesitan para ejecutarlo (por ejemplo: ¿los usuarios solo necesitan el propio Kit de desarrollo de Quantum o necesitan software adicional, como node.js?):</span><span class="sxs-lookup"><span data-stu-id="38957-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="38957-128">Con todo lo que haya en su lugar, puede indicar a los usuarios cómo ejecutar el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="38957-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="38957-129">Por último, es útil indicar a los usuarios qué hace cada archivo en el ejemplo y dónde pueden ir para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="38957-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="38957-130">Asegúrese de usar direcciones URL absolutas aquí, ya que el ejemplo aparecerá en una dirección URL diferente cuando se represente en docs.microsoft.com/samples.</span><span class="sxs-lookup"><span data-stu-id="38957-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
