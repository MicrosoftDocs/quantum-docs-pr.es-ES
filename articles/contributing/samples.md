---
title: Contribución de ejemplos a Microsoft QDK
description: Obtenga información sobre cómo colaborar en el Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024158"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>Contribución de ejemplos al kit de desarrollo de Quantum

Si está interesado en colaborar en el código del [repositorio de ejemplos](https://github.com/Microsoft/Quantum), gracias por hacer que la comunidad Quantum Development sea un lugar mejor.

## <a name="the-quantum-development-kit-samples-repository"></a>Repositorio de ejemplos del kit de desarrollo de Quantum

Para ayudarle a preparar su contribución para ayudar lo máximo posible, es útil echar un vistazo a cómo se diseña el repositorio de ejemplos:

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

Es decir, los ejemplos del [repositorio Microsoft/Quantum](https://github.com/microsoft/Quantum) se desglosan por áreas temáticas en carpetas diferentes, como `algorithms/`, `arithmetic/`o `characterization/`.
Dentro de la carpeta de cada área de asunto, cada ejemplo consta de una única carpeta que recopila todo lo que un usuario necesitará para explorar y usar ese ejemplo.

## <a name="how-samples-are-structured"></a>Cómo se estructuran los ejemplos

Examinando los archivos que componen cada carpeta, vamos a profundizar en el ejemplo de [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) .

| Archivo              | Descripción                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Proyecto de Q # usado para generar el ejemplo con el SDK de .NET Core |
| `Game.qs`         | Operaciones de Q # y funciones para el ejemplo                 |
| `Host.cs`         | C#programa host que se usa para ejecutar el ejemplo                     |
| `host.py`         | Programa host de Python que se usa para ejecutar el ejemplo                 |
| `README.md`       | Documentación sobre lo que hace el ejemplo y cómo usarlo    |

No todas las muestras tendrán exactamente el mismo conjunto de archivos (por ejemplo, algunos ejemplos pueden ser C#solo, otros pueden no tener un host de Python o algunos ejemplos pueden requerir que los archivos de datos de auxiliar funcionen).

## <a name="anatomy-of-a-helpful-readme-file"></a>Anatomía de un archivo Léame útil

Sin embargo, un archivo especialmente importante es el archivo `README.md`, ya que eso es lo que los usuarios necesitan para empezar a trabajar con el ejemplo.

Cada `README.md` debe comenzar con algunos metadatos que ayuden a docs.microsoft.com/samples a encontrar su contribución.

> [!div class="nextstepaction"]
> [Vea cómo se representa el ejemplo chsh-Game.](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Estos metadatos se proporcionan como un [encabezado YAML](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) que indica qué idiomas cubre el ejemplo (normalmente, se `qsharp`, `csharp`y `python`) y qué productos cubre el ejemplo (normalmente solo `qdk`).

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> La clave `page_type: sample` del encabezado es necesaria para que el ejemplo aparezca en docs.microsoft.com/samples.
> Del mismo modo, las claves `product` y `language` son fundamentales para ayudar a los usuarios a encontrar y ejecutar el ejemplo.

Después, es útil proporcionar una breve introducción que indique lo que hace el nuevo ejemplo:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

Los usuarios de su ejemplo también apreciarán saber lo que necesitan para ejecutarlo (por ejemplo: ¿los usuarios solo necesitan el propio Kit de desarrollo de Quantum o necesitan software adicional, como node. js?):

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

Con todo lo que haya en su lugar, puede indicar a los usuarios cómo ejecutar el ejemplo:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Por último, es útil indicar a los usuarios qué hace cada archivo en el ejemplo y dónde pueden ir para obtener más información:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Asegúrese de usar direcciones URL absolutas aquí, ya que el ejemplo aparecerá en una dirección URL diferente cuando se represente en docs.microsoft.com/samples.