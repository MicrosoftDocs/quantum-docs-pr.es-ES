---
title: Introducción a la biblioteca de química cuántica
description: Obtenga información sobre la biblioteca de química cuántica de Microsoft y cómo se usa para simular problemas de estructura electrónica en equipos cuánticos.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: 4268eafa5e53c0a026d179503ac6db88652a8f90
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273682"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a><span data-ttu-id="c2f82-103">Introducción a la biblioteca de química cuántica</span><span class="sxs-lookup"><span data-stu-id="c2f82-103">Introduction to the Quantum Chemistry Library</span></span>

<span data-ttu-id="c2f82-104">La simulación de sistemas físicos juega un papel primordial en la computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="c2f82-104">Simulation of physical systems has long played a central role in quantum computing.</span></span>  <span data-ttu-id="c2f82-105">Esto se debe a que la dinámica cuántica se considera inextricable para realizar simulaciones en equipos cuánticos, lo que significa que la complejidad de la simulación del sistema aumenta exponencialmente con el tamaño del sistema cuántico en cuestión.</span><span class="sxs-lookup"><span data-stu-id="c2f82-105">This is because quantum dynamics are widely believed to be intractable to simulate on quantum computers, meaning that the complexity of simulating the system scales exponentially with the size of the quantum system in question.</span></span>  <span data-ttu-id="c2f82-106">La simulación de problemas en química y ciencia de materiales sigue siendo posiblemente la aplicación más evocadora de la computación cuántica y nos permitirá probar mecanismos de reacción química que hasta la fecha estaban fuera de nuestra capacidad de medir o simular.</span><span class="sxs-lookup"><span data-stu-id="c2f82-106">Simulating problems in chemistry and material science remains perhaps the most evocative application of quantum computing and would allow us to probe chemical reaction mechanisms that hitherto were beyond our ability to measure or simulate.</span></span>  <span data-ttu-id="c2f82-107">También nos permitirá simular materiales electrónicos correlacionados, como superconductores a alta temperatura.</span><span class="sxs-lookup"><span data-stu-id="c2f82-107">It would also allow us to simulate correlated electronic materials such as high-temperature superconductors.</span></span> <span data-ttu-id="c2f82-108">La lista de aplicaciones en este espacio es inmensa.</span><span class="sxs-lookup"><span data-stu-id="c2f82-108">The list of applications in this space is vast.</span></span>

<span data-ttu-id="c2f82-109">El objetivo de esta documentación es proporcionar una introducción concisa a la simulación de problemas de estructura electrónica en equipos cuánticos para ayudar al lector a comprender el rol que muchos aspectos de la biblioteca de simulación de funciones de Hamilton desempeñan en el espacio.</span><span class="sxs-lookup"><span data-stu-id="c2f82-109">The purpose of this documentation is to provide a concise introduction to simulating electronic structure problems on quantum computers in order to help the reader understand the role that many aspects of the Hamiltonian simulation library play within the space.</span></span>  <span data-ttu-id="c2f82-110">Comenzamos con una breve introducción a la mecánica cuántica y luego continuaremos con el análisis de cómo se modelan los sistemas electrónicos en ella.</span><span class="sxs-lookup"><span data-stu-id="c2f82-110">We begin with a brief introduction to quantum mechanics and then proceed to discuss how electronic systems are modeled in it.</span></span>  <span data-ttu-id="c2f82-111">A continuación, veremos cómo se puede emular dicha dinámica cuántica con un equipo cuántico.</span><span class="sxs-lookup"><span data-stu-id="c2f82-111">We will then discuss how such quantum dynamics can be emulated using a quantum computer.</span></span>  <span data-ttu-id="c2f82-112">Tras ello, se tratarán dos métodos que se usan para compilar la dinámica cuántica en secuencias de puertas elementales: Las descomposiciones de Trotter-Suzuki y la qubitización.</span><span class="sxs-lookup"><span data-stu-id="c2f82-112">Once this is complete we will discuss two methods used to compile the quantum dynamics to sequences of elementary gates: Trotter-Suzuki decompositions and qubitization.</span></span>