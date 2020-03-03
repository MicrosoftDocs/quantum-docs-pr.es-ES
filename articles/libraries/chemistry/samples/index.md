---
title: Aplicaciones de ejemplo de química cuántica
description: Explore las aplicaciones de ejemplo de la biblioteca de química cuántica de Microsoft.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906498"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="2547a-103">Ejemplos de química cuántica</span><span class="sxs-lookup"><span data-stu-id="2547a-103">Quantum chemistry examples</span></span>

<span data-ttu-id="2547a-104">En los conceptos de química cuántica, creamos manualmente ejemplos de funciones de Hamilton fermiónicas.</span><span class="sxs-lookup"><span data-stu-id="2547a-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="2547a-105">Ahora combinamos los algoritmos de simulación de química descritos en [Simulación de dinámica de funciones de Hamilton](xref:microsoft.quantum.libraries.standard.algorithms) con la [estimación de la fase cuántica](xref:microsoft.quantum.libraries.characterization) en la biblioteca de Canon.</span><span class="sxs-lookup"><span data-stu-id="2547a-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="2547a-106">Esta combinación nos permite obtener estimaciones de niveles de energía en la molécula representada, que es una de las aplicaciones clave de la química cuántica en un equipo cuántico.</span><span class="sxs-lookup"><span data-stu-id="2547a-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="2547a-107">En lugar de especificar los términos de la función de Hamilton de uno en uno, también trabajamos en algunos ejemplos que nos permiten realizar experimentos de química cuántica a escala.</span><span class="sxs-lookup"><span data-stu-id="2547a-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="2547a-108">Comenzamos con ejemplos que cargan una función de Hamilton de química codificada en el [esquema de Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span><span class="sxs-lookup"><span data-stu-id="2547a-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="2547a-109">En el caso de las moléculas que son demasiado grandes para simular en el [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), todavía se pueden llevar a cabo operaciones científicas interesantes.</span><span class="sxs-lookup"><span data-stu-id="2547a-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="2547a-110">Por ejemplo, los costos de recursos de la realización de simulaciones de química de gran envergadura se pueden seguir evaluando con el [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="2547a-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="2547a-111">Ahora ilustraremos algunas aplicaciones interesantes de la biblioteca de simulación de química con algunos de los ejemplos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="2547a-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>
