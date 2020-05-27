---
title: Creación de un generador cuántico de números aleatorios
description: Cree un proyecto de Q# para crear un generador cuántico de números aleatorios con el fin de mostrar los conceptos cuánticos fundamentales tales como la superposición.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 3e109553adc4d724733834e3660bfe7789052bcf
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426818"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Tutorial: Implementación de un generador cuántico de números aleatorios en Q\#

Un ejemplo sencillo de un algoritmo cuántico escrito en Q# es un generador cuántico de números aleatorios. Este algoritmo aprovecha la naturaleza de la mecánica cuántica para generar un número aleatorio.

## <a name="prerequisites"></a>Prerrequisitos

- [Kit de desarrollo de Microsoft Quantum](xref:microsoft.quantum.install).
- [Creación de un proyecto de Q#](xref:microsoft.quantum.howto.createproject)

## <a name="write-a-q-operation"></a>Escriba una operación de Q#

### <a name="q-operation-code"></a>Código de operación de Q#

1. Reemplace el contenido del archivo Program.qs por el código siguiente:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

Tal y como se mencionó en nuestro artículo [Descripción de la computación cuántica](xref:microsoft.quantum.overview.understanding), un cúbit es una unidad de información cuántica que puede estar en superposición. Cuando se mide, un cúbit solo puede ser 0 o 1. Sin embargo, durante la ejecución, el estado del cúbit representa la probabilidad de leer un 0 o un 1 al tomar una medida. Este estado probabilístico se conoce como superposición. Podemos usar esta probabilidad para generar números aleatorios.

En nuestra operación de Q#, presentamos el tipo de datos `Qubit`, nativo de Q#. Solo se puede asignar un `Qubit` con una instrucción `using`. Cuando se asigna un cúbit, siempre está en el estado `Zero`. 

Con la operación `H`, podemos poner nuestro `Qubit` en superposición. Para medir un cúbit y leer su valor, se usa la operación intrínseca `M`.

Al poner el `Qubit` en superposición y medirlo, el resultado será un valor diferente cada vez que se invoque el código.

Cuando se desasigna un `Qubit`, se debe volver a poner explícitamente en el estado `Zero`; de lo contrario, el simulador informará de un error de tiempo de ejecución. Una manera fácil de hacerlo es invocar a `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Visualización del código con la esfera de Bloch

En la esfera Bloch, el polo norte representa el valor clásico **0** y el polo sur representa el valor clásico **1**. Cualquier superposición se puede representar mediante un punto en la esfera (representado con una flecha). Cuanto más cerca esté el extremo de la flecha a un polo, mayor será la probabilidad de que el cúbit caiga en el valor clásico asignado a ese polo cuando se mida. Por ejemplo, el estado del cúbit representado por la flecha roja siguiente tiene una mayor probabilidad de dar el valor **0** si lo medimos.

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

Podemos usar esta representación para visualizar lo que está haciendo el código:

* En primer lugar, empezamos con un cúbit inicializado en el estado **0** y aplicamos `H` para crear una superposición en la que las probabilidades de **0** y **1** sean las mismas.

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* A continuación, se mide el cúbit y se guarda el resultado:

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

Como el resultado de la medida es completamente aleatorio, hemos obtenido un bit aleatorio. Podemos llamar a esta operación varias veces para crear enteros. Por ejemplo, si llamamos a la operación tres veces para obtener tres bits aleatorios, podemos crear números de 3 bits aleatorios (es decir, un número aleatorio entre 0 y 7).


## <a name="creating-a-complete-random-number-generator"></a>Creación de un generador completo de números aleatorios

Ahora que tenemos una operación de Q# que genera bits aleatorios, podemos usarlo para crear un generador completo de números cuánticos aleatorios. Podemos usar las aplicaciones de línea de comandos de Q# o usar un programa host.



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[Aplicaciones de línea de comandos de Q# con Visual Studio o Visual Studio Code](#tab/tabid-qsharp)

Para crear la aplicación de línea de comandos de Q# completa, agregue el siguiente punto de entrada al programa de Q#: 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

El ejecutable ejecutará la operación o función marcada con el atributo `@EntryPoint()` en un simulador o una calculadora de recursos, dependiendo de la configuración del proyecto y de las opciones de la línea de comandos.

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

En Visual Studio, solo tiene que presionar Ctrl+F5 para ejecutar el script.

En VS Code, escriba lo siguiente en el terminal para compilar el archivo Program.qs la primera vez:

```dotnetcli
dotnet build
```

En las ejecuciones posteriores, no es necesario volver a compilarlo. Para ejecutarlo, escriba el siguiente comando y presione Entrar:

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python con Visual Studio Code o la línea de comandos](#tab/tabid-python)

Para ejecutar el nuevo programa de Q# desde Python, guarde el código siguiente como `host.py`:

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

A continuación, puede ejecutar el programa host de Python desde la línea de comandos:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[C# con Visual Studio Code o Visual Studio](#tab/tabid-csharp)

Para ejecutar el nuevo programa de Q# desde C#, modifique `Driver.cs` para incluir el siguiente código de C#:

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

A continuación, puede ejecutar el programa host de C# desde la línea de comandos (en Visual Studio, presione F5):

```bash
$ dotnet run
The random number generated is 42
```

***
