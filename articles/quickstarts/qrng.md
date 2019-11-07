---
title: Creación de un generador cuántico de números aleatorios
description: Cree un proyecto de Q# para crear un generador cuántico de números aleatorios con el fin de mostrar los conceptos cuánticos fundamentales tales como la superposición.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: c3039b92c4b3235a397d5cf31280ac2673706e9d
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462845"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Inicio rápido: Implementación de un generador cuántico de números aleatorios en Q#
Un ejemplo sencillo de un algoritmo cuántico escrito en Q# es un generador cuántico de números aleatorios. Este algoritmo aprovecha la naturaleza de la mecánica cuántica para generar un número aleatorio. 

## <a name="prerequisites"></a>Requisitos previos

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Creación de un proyecto de Q#](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Escriba una operación de Q#

### <a name="q-operation-code"></a>Código de operación de Q#

1. Reemplace el contenido del archivo Operation.qs por el código siguiente:

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

Tal y como se mencionó en nuestro artículo [¿Qué es computación cuántica?](xref:microsoft.quantum.overview.what), un qubit es una unidad de información cuántica que puede estar en superposición. Cuando se mide, un qubit solo puede ser 0 o 1. Sin embargo, durante la ejecución, el estado del qubit representa la probabilidad de leer un 0 o un 1 al tomar una medida. Este estado probabilístico se conoce como superposición. Podemos usar esta probabilidad para generar números aleatorios.

En nuestra operación de Q#, presentamos el tipo de datos `Qubit`, nativo de Q#. Solo se puede asignar un `Qubit` con una instrucción `using`. Cuando se asigna un qubit, siempre está en el estado `Zero`. 

Con la operación `H`, podemos poner nuestro `Qubit` en superposición. Para medir un qubit y leer su valor, se usa la operación intrínseca `M`.

Al poner el `Qubit` en superposición y medirlo, el resultado será un valor diferente cada vez que se invoque el código. 

Cuando se desasigna un `Qubit`, se debe volver a poner explícitamente en el estado `Zero`; de lo contrario, el simulador informará de un error de tiempo de ejecución. Una manera fácil de hacerlo es invocar a `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Visualización del código con la esfera de Bloch

En la esfera Bloch, el polo norte representa el valor clásico **0** y el polo sur representa el valor clásico **1**. Cualquier superposición se puede representar mediante un punto en la esfera (representado con una flecha). Cuanto más cerca esté el extremo de la flecha a un polo, mayor será la probabilidad de que el qubit caiga en el valor clásico asignado a ese polo cuando se mida. Por ejemplo, el estado del qubit representado por la flecha roja siguiente tiene una mayor probabilidad de dar el valor **0** si lo medimos.

<img src="./Bloch.svg" width="175">

Podemos usar esta representación para visualizar lo que está haciendo el código:

* En primer lugar, empezamos con un qubit inicializado en el estado **0** y aplicamos `H` para crear una superposición en la que las probabilidades de **0** y **1** sean las mismas.

<img src="./H.svg" width="450">

* A continuación, se mide el qubit y se guarda el resultado:

<img src="./Measurement2.svg" width="450">

Como el resultado de la medida es completamente aleatorio, hemos obtenido un bit aleatorio. Podemos llamar a esta operación varias veces para crear enteros. Por ejemplo, si llamamos a la operación tres veces para obtener tres bits aleatorios, podemos crear números de 3 bits aleatorios (es decir, un número aleatorio entre 0 y 7).
