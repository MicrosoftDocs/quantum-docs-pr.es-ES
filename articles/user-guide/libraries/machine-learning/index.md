---
title: Introducción al paquete de aprendizaje automático cuántico | Microsoft Docs
description: Introducción al paquete de aprendizaje automático cuántico
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: conceptual
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1e36948a216a06d76b99cd451bbfac6f5defd7c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858789"
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
