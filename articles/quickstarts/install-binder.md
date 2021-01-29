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
# <a name="develop-with-no-locq-and-binder"></a>Desarrollo con Q# y Binder

Puede usar Binder para ejecutar y compartir sus cuadernos de Jupyter Notebook en línea.

## <a name="use-binder-with-the-microsoft-qdk-samples"></a>Uso de Binder con los ejemplos de Microsoft QDK

Para configurar Binder automáticamente para usar los ejemplos de Microsoft QDK:

1. Abra un explorador y ejecute https://aka.ms/try-qsharp.
1. En la página de aterrizaje **Ejemplos del kit de desarrollo de Quantum**, haga clic en **cuaderno de Q#** para aprender a usar IQ# para escribir sus propios cuadernos de aplicación cuántica.

![Página de aterrizaje del QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a>Uso de Binder con sus propios cuadernos y repositorios

Si ya tiene cuadernos en un repositorio de GitHub, puede configurar Binder para que funcione con su repositorio:

1. Asegúrese de que haya un archivo llamado *Dockerfile* en el directorio raíz del repositorio. El archivo debe contener al menos las siguientes líneas:

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > Puede consultar cuál es la versión más reciente de IQ# en las [notas de la versión](xref:microsoft.quantum.relnotes).

    Para más información sobre cómo crear un archivo Dockerfile, consulte la [referencia de Dockerfile](https://docs.docker.com/engine/reference/builder/).

2. Abra un explorador en [mybinder.org](https://mybinder.org).
3. Escriba el nombre del repositorio como una **dirección URL de GitHub** (por ejemplo, *miNombre/miRepositorio*) y haga clic en **launch** (Iniciar).

![Formulario de MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a>Pasos siguientes

Ahora que ha configurado el entorno de Binder, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).
