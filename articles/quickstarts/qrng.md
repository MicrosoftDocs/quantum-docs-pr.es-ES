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
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="3752b-103">Inicio rápido: Implementación de un generador cuántico de números aleatorios en Q#</span><span class="sxs-lookup"><span data-stu-id="3752b-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="3752b-104">Un ejemplo sencillo de un algoritmo cuántico escrito en Q# es un generador cuántico de números aleatorios.</span><span class="sxs-lookup"><span data-stu-id="3752b-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="3752b-105">Este algoritmo aprovecha la naturaleza de la mecánica cuántica para generar un número aleatorio.</span><span class="sxs-lookup"><span data-stu-id="3752b-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3752b-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3752b-106">Prerequisites</span></span>

- <span data-ttu-id="3752b-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="3752b-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="3752b-108">Creación de un proyecto de Q#</span><span class="sxs-lookup"><span data-stu-id="3752b-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="3752b-109">Escriba una operación de Q#</span><span class="sxs-lookup"><span data-stu-id="3752b-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="3752b-110">Código de operación de Q#</span><span class="sxs-lookup"><span data-stu-id="3752b-110">Q# operation code</span></span>

1. <span data-ttu-id="3752b-111">Reemplace el contenido del archivo Operation.qs por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3752b-111">Replace the contents of the Operation.qs file with the following code:</span></span>

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

<span data-ttu-id="3752b-112">Tal y como se mencionó en nuestro artículo [¿Qué es computación cuántica?](xref:microsoft.quantum.overview.what), un qubit es una unidad de información cuántica que puede estar en superposición.</span><span class="sxs-lookup"><span data-stu-id="3752b-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="3752b-113">Cuando se mide, un qubit solo puede ser 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="3752b-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="3752b-114">Sin embargo, durante la ejecución, el estado del qubit representa la probabilidad de leer un 0 o un 1 al tomar una medida.</span><span class="sxs-lookup"><span data-stu-id="3752b-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="3752b-115">Este estado probabilístico se conoce como superposición.</span><span class="sxs-lookup"><span data-stu-id="3752b-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="3752b-116">Podemos usar esta probabilidad para generar números aleatorios.</span><span class="sxs-lookup"><span data-stu-id="3752b-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="3752b-117">En nuestra operación de Q#, presentamos el tipo de datos `Qubit`, nativo de Q#.</span><span class="sxs-lookup"><span data-stu-id="3752b-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="3752b-118">Solo se puede asignar un `Qubit` con una instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="3752b-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="3752b-119">Cuando se asigna un qubit, siempre está en el estado `Zero`.</span><span class="sxs-lookup"><span data-stu-id="3752b-119">When it gets allocated a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="3752b-120">Con la operación `H`, podemos poner nuestro `Qubit` en superposición.</span><span class="sxs-lookup"><span data-stu-id="3752b-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="3752b-121">Para medir un qubit y leer su valor, se usa la operación intrínseca `M`.</span><span class="sxs-lookup"><span data-stu-id="3752b-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="3752b-122">Al poner el `Qubit` en superposición y medirlo, el resultado será un valor diferente cada vez que se invoque el código.</span><span class="sxs-lookup"><span data-stu-id="3752b-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="3752b-123">Cuando se desasigna un `Qubit`, se debe volver a poner explícitamente en el estado `Zero`; de lo contrario, el simulador informará de un error de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3752b-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="3752b-124">Una manera fácil de hacerlo es invocar a `Reset`.</span><span class="sxs-lookup"><span data-stu-id="3752b-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="3752b-125">Visualización del código con la esfera de Bloch</span><span class="sxs-lookup"><span data-stu-id="3752b-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="3752b-126">En la esfera Bloch, el polo norte representa el valor clásico **0** y el polo sur representa el valor clásico **1**.</span><span class="sxs-lookup"><span data-stu-id="3752b-126">In the Bloch sphere the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="3752b-127">Cualquier superposición se puede representar mediante un punto en la esfera (representado con una flecha).</span><span class="sxs-lookup"><span data-stu-id="3752b-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="3752b-128">Cuanto más cerca esté el extremo de la flecha a un polo, mayor será la probabilidad de que el qubit caiga en el valor clásico asignado a ese polo cuando se mida.</span><span class="sxs-lookup"><span data-stu-id="3752b-128">When the closer the end of the arrow to a pole, the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="3752b-129">Por ejemplo, el estado del qubit representado por la flecha roja siguiente tiene una mayor probabilidad de dar el valor **0** si lo medimos.</span><span class="sxs-lookup"><span data-stu-id="3752b-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="./Bloch.svg" width="175">

<span data-ttu-id="3752b-130">Podemos usar esta representación para visualizar lo que está haciendo el código:</span><span class="sxs-lookup"><span data-stu-id="3752b-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="3752b-131">En primer lugar, empezamos con un qubit inicializado en el estado **0** y aplicamos `H` para crear una superposición en la que las probabilidades de **0** y **1** sean las mismas.</span><span class="sxs-lookup"><span data-stu-id="3752b-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="./H.svg" width="450">

* <span data-ttu-id="3752b-132">A continuación, se mide el qubit y se guarda el resultado:</span><span class="sxs-lookup"><span data-stu-id="3752b-132">Then we measure the qubit and save the output:</span></span>

<img src="./Measurement2.svg" width="450">

<span data-ttu-id="3752b-133">Como el resultado de la medida es completamente aleatorio, hemos obtenido un bit aleatorio.</span><span class="sxs-lookup"><span data-stu-id="3752b-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="3752b-134">Podemos llamar a esta operación varias veces para crear enteros.</span><span class="sxs-lookup"><span data-stu-id="3752b-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="3752b-135">Por ejemplo, si llamamos a la operación tres veces para obtener tres bits aleatorios, podemos crear números de 3 bits aleatorios (es decir, un número aleatorio entre 0 y 7).</span><span class="sxs-lookup"><span data-stu-id="3752b-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>
