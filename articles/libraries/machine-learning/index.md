---
title: Introducción al paquete de aprendizaje automático cuántico | Microsoft Docs
description: Introducción al paquete de aprendizaje automático cuántico
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
ms.openlocfilehash: 7f22d5d3212890abc764f88693937b534466170f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907858"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="90c28-103">Introducción a la biblioteca de aprendizaje automático cuántico</span><span class="sxs-lookup"><span data-stu-id="90c28-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="90c28-104">La biblioteca de aprendizaje automático cuántico es una API escrita en Q# que ofrece la posibilidad de ejecutar experimentos de aprendizaje automático híbridos clásicos y cuánticos.</span><span class="sxs-lookup"><span data-stu-id="90c28-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="90c28-105">La biblioteca permite:</span><span class="sxs-lookup"><span data-stu-id="90c28-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="90c28-106">Cargar sus propios datos para clasificarlos con simuladores cuánticos.</span><span class="sxs-lookup"><span data-stu-id="90c28-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="90c28-107">Usar ejemplos y tutoriales para introducirse en el campo del aprendizaje automático cuántico.</span><span class="sxs-lookup"><span data-stu-id="90c28-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="90c28-108">Es de esperar un rendimiento bajo en comparación con las plataformas de aprendizaje automático clásicas actuales (recuerde que todo se ejecuta en la simulación de un dispositivo cuántico, que ya es costoso desde el punto de vista del cálculo).</span><span class="sxs-lookup"><span data-stu-id="90c28-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="90c28-109">El objetivo de este documento es:</span><span class="sxs-lookup"><span data-stu-id="90c28-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="90c28-110">Servir de introducción concisa a las herramientas de aprendizaje automático (escritas en Q\#) para el aprendizaje híbrido cuántico y clásico.</span><span class="sxs-lookup"><span data-stu-id="90c28-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="90c28-111">Presentar los conceptos de aprendizaje automático y, concretamente, su aplicación en clasificadores cuánticos centrados en circuitos (también conocidos como clasificadores cuánticos secuenciales).</span><span class="sxs-lookup"><span data-stu-id="90c28-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="90c28-112">Ofrecer un conjunto de tutoriales acerca de los aspectos básicos para empezar a usar las herramientas que la biblioteca proporciona.</span><span class="sxs-lookup"><span data-stu-id="90c28-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="90c28-113">Analizar los métodos de entrenamiento y validación de estos clasificadores y cómo se traducen en las operaciones de Q\# específicas proporcionadas por la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="90c28-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="90c28-114">El modelo implementado en esta biblioteca se basa en el esquema de aprendizaje automático cuántico-clásico presentado en [Clasificadores cuánticos centrados en circuitos](https://arxiv.org/abs/1804.00633).</span><span class="sxs-lookup"><span data-stu-id="90c28-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
