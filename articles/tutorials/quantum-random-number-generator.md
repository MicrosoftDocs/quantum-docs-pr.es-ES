---
title: Creación de un generador cuántico de números aleatorios
description: Cree un Q# proyecto que muestre conceptos fundamentales de Quantum como la superposición mediante la creación de un generador de números aleatorios Quantum.
author: bromeg
ms.author: megbrow
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: cefe35a10dd89c14d2f1abc3080d52ab125236d1
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771270"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Tutorial: Implementación de un generador cuántico de números aleatorios en Q\#

Un ejemplo sencillo de un algoritmo Quantum escrito en Q# es un generador de números aleatorios Quantum. Este algoritmo aprovecha la naturaleza de la mecánica cuántica para generar un número aleatorio.

## <a name="prerequisites"></a>Prerrequisitos

- [Kit de desarrollo de Microsoft Quantum](xref:microsoft.quantum.install).
- Cree un Q# proyecto para una [ Q# aplicación](xref:microsoft.quantum.install.standalone), con un [programa host de Python](xref:microsoft.quantum.install.python)o un [programa host de C#](xref:microsoft.quantum.install.cs).

## <a name="write-a-no-locq-operation"></a>Escribir una Q# operación

### <a name="no-locq-operation-code"></a>Q# código de operación

1. Reemplace el contenido del archivo Program.qs por el código siguiente:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

Tal y como se mencionó en nuestro artículo [Descripción de la computación cuántica](xref:microsoft.quantum.overview.understanding), un cúbit es una unidad de información cuántica que puede estar en superposición. Cuando se mide, un cúbit solo puede ser 0 o 1. Sin embargo, antes de la medida, el estado de qubit representa la probabilidad de leer un 0 o un 1 con una medida. Este estado probabilístico se conoce como superposición. Podemos usar esta probabilidad para generar números aleatorios.

En nuestra Q# operación, se introduce el tipo de la forma `Qubit` , nativo en Q# . Solo se puede asignar un `Qubit` con una instrucción `using`. Cuando se asigna un cúbit, siempre está en el estado `Zero`. 

Con la operación `H`, podemos poner nuestro `Qubit` en superposición. Para medir un cúbit y leer su valor, se usa la operación intrínseca `M`.

Al poner el `Qubit` en superposición y medirlo, el resultado será un valor diferente cada vez que se invoque el código.

Cuando se desasigna un `Qubit`, se debe volver a establecer explícitamente en el estado `Zero`; de lo contrario, el simulador notificará un error en tiempo de ejecución. Una manera fácil de hacerlo es invocar a `Reset`.

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

Ahora que tenemos una Q# operación que genera bits aleatorios, se puede usar para crear un generador de números aleatorios Quantum completo. Se puede usar una Q# aplicación o usar un programa host.



### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>[Q# aplicaciones con Visual Studio o Visual Studio Code](#tab/tabid-qsharp)

Para crear la Q# aplicación completa, agregue el siguiente punto de entrada al Q# programa: 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

El programa ejecutará la operación o función marcada con el `@EntryPoint()` atributo en un simulador o estimador de recursos, en función de la configuración del proyecto y las opciones de la línea de comandos.

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

En Visual Studio, simplemente presione Ctrl + F5 para ejecutar el script.

En VS Code, escriba lo siguiente en el terminal para compilar el archivo Program.qs la primera vez:

```dotnetcli
dotnet build
```

En las ejecuciones posteriores, no es necesario volver a compilarlo. Para ejecutarlo, escriba el siguiente comando y presione Entrar:

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-prompt"></a>[Python con Visual Studio Code o el símbolo del sistema](#tab/tabid-python)

Para ejecutar el nuevo Q# programa desde Python, guarde el código siguiente como `host.py` :

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

Después, puede ejecutar el programa host de Python desde el símbolo del sistema:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[C# con Visual Studio Code o Visual Studio](#tab/tabid-csharp)

Para ejecutar el nuevo Q# programa desde C#, modifique `Driver.cs` para incluir el siguiente código de c#:

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

Después, puede ejecutar el programa host de C# desde el símbolo del sistema (en Visual Studio, debe presionar F5):

```bash
$ dotnet run
The random number generated is 42
```

***
