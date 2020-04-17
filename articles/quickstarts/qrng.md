---
title: Creación de un generador cuántico de números aleatorios
description: Cree un proyecto de Q# para crear un generador cuántico de números aleatorios con el fin de mostrar los conceptos cuánticos fundamentales tales como la superposición.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: b9c8592b1296a7de1b9ad5d0538ad1972ec25e31
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906991"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Inicio rápido: Implementación de un generador cuántico de números aleatorios en Q#
Un ejemplo sencillo de un algoritmo cuántico escrito en Q# es un generador cuántico de números aleatorios. Este algoritmo aprovecha la naturaleza de la mecánica cuántica para generar un número aleatorio. 

## <a name="prerequisites"></a>Prerrequisitos

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Creación de un proyecto de Q#](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Escriba una operación de Q#

### <a name="q-operation-code"></a>Código de operación de Q#

1. Reemplace el contenido del archivo Operation.qs por el código siguiente:

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

Tal y como se mencionó en nuestro artículo [¿Qué es computación cuántica?](xref:microsoft.quantum.overview.what), un qubit es una unidad de información cuántica que puede estar en superposición. Cuando se mide, un qubit solo puede ser 0 o 1. Sin embargo, durante la ejecución, el estado del qubit representa la probabilidad de leer un 0 o un 1 al tomar una medida. Este estado probabilístico se conoce como superposición. Podemos usar esta probabilidad para generar números aleatorios.

En nuestra operación de Q#, presentamos el tipo de datos `Qubit`, nativo de Q#. Solo se puede asignar un `Qubit` con una instrucción `using`. Cuando se asigna un qubit, siempre está en el estado `Zero`. 

Con la operación `H`, podemos poner nuestro `Qubit` en superposición. Para medir un qubit y leer su valor, se usa la operación intrínseca `M`.

Al poner el `Qubit` en superposición y medirlo, el resultado será un valor diferente cada vez que se invoque el código. 

Cuando se desasigna un `Qubit`, se debe volver a poner explícitamente en el estado `Zero`; de lo contrario, el simulador informará de un error de tiempo de ejecución. Una manera fácil de hacerlo es invocar a `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Visualización del código con la esfera de Bloch

En la esfera Bloch, el polo norte representa el valor clásico **0** y el polo sur representa el valor clásico **1**. Cualquier superposición se puede representar mediante un punto en la esfera (representado con una flecha). Cuanto más cerca esté el extremo de la flecha a un polo, mayor será la probabilidad de que el qubit caiga en el valor clásico asignado a ese polo cuando se mida. Por ejemplo, el estado del qubit representado por la flecha roja siguiente tiene una mayor probabilidad de dar el valor **0** si lo medimos.

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

Podemos usar esta representación para visualizar lo que está haciendo el código:

* En primer lugar, empezamos con un qubit inicializado en el estado **0** y aplicamos `H` para crear una superposición en la que las probabilidades de **0** y **1** sean las mismas.

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">


* A continuación, se mide el qubit y se guarda el resultado:

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

Como el resultado de la medida es completamente aleatorio, hemos obtenido un bit aleatorio. Podemos llamar a esta operación varias veces para crear enteros. Por ejemplo, si llamamos a la operación tres veces para obtener tres bits aleatorios, podemos crear números de 3 bits aleatorios (es decir, un número aleatorio entre 0 y 7).

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a>Creación de un generador completo de números aleatorios mediante un programa host

Ahora que tenemos una operación de Q# que genera bits aleatorios, podemos usarlo para crear un generador completo de números cuánticos aleatorios con un programa host.

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python con Visual Studio Code o la línea de comandos](#tab/tabid-python)
 
 Para ejecutar el nuevo programa de Q# desde Python, guarde el código siguiente como `host.py`:
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 A continuación, puede ejecutar el programa host de Python desde la línea de comandos:
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# con Visual Studio Code o la línea de comandos](#tab/tabid-csharp)
 
 Para ejecutar el nuevo programa de Q# desde C#, modifique `Driver.cs` para incluir el siguiente código de C#:
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 A continuación, puede ejecutar el programa host de C# desde la línea de comandos:
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[C# con Visual Studio 2019](#tab/tabid-vs2019)

 Para ejecutar el nuevo programa de Q# desde C# en Visual Studio, modifique `Driver.cs` para que incluya el código C# siguiente:

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 Después, presione F5; el programa iniciará la ejecución y se mostrará una nueva ventana con el número aleatorio generado: 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
