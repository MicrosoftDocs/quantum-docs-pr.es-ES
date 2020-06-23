---
title: Introducción al paquete de aprendizaje automático cuántico | Microsoft Docs
description: Introducción al paquete de aprendizaje automático cuántico
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
ms.openlocfilehash: 7f22d5d3212890abc764f88693937b534466170f
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274004"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>Introducción a la biblioteca de aprendizaje automático cuántico

La biblioteca de aprendizaje automático cuántico es una API escrita en Q# que ofrece la posibilidad de ejecutar experimentos de aprendizaje automático híbridos clásicos y cuánticos. La biblioteca permite:

- Cargar sus propios datos para clasificarlos con simuladores cuánticos.

- Usar ejemplos y tutoriales para introducirse en el campo del aprendizaje automático cuántico.

Es de esperar un rendimiento bajo en comparación con las plataformas de aprendizaje automático clásicas actuales (recuerde que todo se ejecuta en la simulación de un dispositivo cuántico, que ya es costoso desde el punto de vista del cálculo).

El objetivo de este documento es:

- Servir de introducción concisa a las herramientas de aprendizaje automático (escritas en Q\#) para el aprendizaje híbrido cuántico y clásico.
- Presentar los conceptos de aprendizaje automático y, concretamente, su aplicación en clasificadores cuánticos centrados en circuitos (también conocidos como clasificadores cuánticos secuenciales).
- Ofrecer un conjunto de tutoriales acerca de los aspectos básicos para empezar a usar las herramientas que la biblioteca proporciona.
- Analizar los métodos de entrenamiento y validación de estos clasificadores y cómo se traducen en las operaciones de Q\# específicas proporcionadas por la biblioteca.

El modelo implementado en esta biblioteca se basa en el esquema de aprendizaje automático cuántico-clásico presentado en [Clasificadores cuánticos centrados en circuitos](https://arxiv.org/abs/1804.00633).
