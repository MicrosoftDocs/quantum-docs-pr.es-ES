---
title: ¿Qué pueden hacer los equipos cuánticos?
description: Obtenga información sobre el impacto de la computación cuántica, desde novedosos algoritmos cuánticos hasta algoritmos de inspiración cuántica que se ejecutan en equipos clásicos.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: d4be970c635ca090e8dcb1b58d5c840eebd4d110
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443841"
---
# <a name="what-can-a-quantum-computer-do"></a>¿Qué pueden hacer los equipos cuánticos?

¿Qué se puede hacer con un equipo cuántico que no se pueda hacer con uno clásico?

Para resolver algunos de los problemas más desafiantes del mundo, en los que la búsqueda de una solución podría llevar miles de millones de años a un equipo actual, un equipo cuántico podría hacerlo en días, horas o incluso minutos. La computación cuántica permitirá a los investigadores desarrollar nuevos catalizadores y materiales, mejorar los medicamentos, acelerar los avances en la inteligencia artificial y responder a las preguntas fundamentales sobre los orígenes de nuestro universo.

## <a name="quantum-simulation"></a>Simulación cuántica

El uso de programas cuánticos para el automodelado de los sistemas cuánticos ofrece enormes posibilidades de desbloquear la información que conducirá a la innovación en muchos sectores. La fotosíntesis, los superconductores y las moléculas complejas son ejemplos de sistemas cuánticos que se pueden simular mediante programas cuánticos.

La simulación de sistemas microscópicos que se comportan de acuerdo con las leyes de la mecánica cuántica es computacionalmente costosa. Es necesario tener en cuenta todos los estados posibles que pueden estar en la superposición y el número de estados aumenta exponencialmente con el tamaño del sistema. En un equipo cuántico, no es necesario modelar todos los estados del sistema. En su lugar, se inserta el estado cuántico del sistema que se desea simular en los qubits del propio equipo y se ejecuta la simulación con un conjunto específico de puertas cuánticas. En otras palabras, usamos un ordenador cuántico para simular un sistema cuántico.

Las moléculas químicas son sistemas cuánticos y, por lo tanto, se pueden analizar de esta manera. Una sustancia química específica es la enzima _nitrogenasa_ que, con una mejor comprensión de sus propiedades, podría tener la posibilidad de reducir el consumo energético y la emisión del gas de efecto invernadero de los fertilizantes actuales.

## <a name="cryptography"></a>Criptografía

Quizás la aplicación más famosa de los equipos cuánticos sea la criptografía. En ella, Peter Shor mostró en 1994 que un equipo cuántico escalable puede vulnerar todas las técnicas de cifrado más usadas.  La criptografía clásica se basa en la irresolubilidad de las operaciones en números grandes, tales como la factorización de números grandes en dos números primos.  La computación cuántica hace que estas operaciones sean teóricamente resolubles (mediante el algoritmo de Shor). Mientras que la implementación de este algoritmo no es físicamente posible con la escala actual del hardware cuántico, ha generado el desarrollo de algoritmos resistentes a la cuántica para la seguridad de los datos de prueba de futuro, incluidos los novedosos algoritmos cuánticos para el cifrado y distribución de claves criptográficas.  En Microsoft, contamos con el mejor equipo del mundo en seguridad y criptografía poscuántica, que desarrollan algoritmos resistentes a la computación cuántica. 

## <a name="optimization"></a>Optimización

La optimización es la tarea de realizar una búsqueda grande en un espacio de grandes dimensiones para obtener una solución realmente buena que minimice una función de costo determinada.   En un equipo cuántico, podemos acelerar los algoritmos de optimización, lo que permite encontrar soluciones que, de otro modo, no serían posibles. Las aplicaciones van desde el transporte y la logística a la asistencia sanitaria, el diagnóstico y la ciencia de los materiales. Puede suponer un impacto profundo en la eficiencia de estos sectores. 

La optimización con computación cuántica nos permite innovar en el ámbito del transporte y la logística de una manera que no es posible con los sistemas clásicos actuales. La optimización del flujo de tráfico puede reducir los atascos.  Además de la planeación de rutas, podemos hablar de asignación de puertas a un avión, entrega de paquetes, programación de trabajos y mucho más.  Con los avances en la ciencia de los materiales, habrá nuevas formas de energía, baterías con mayor capacidad y materiales más sólidos y ligeros. 

## <a name="machine-learning"></a>Machine Learning

Un gran número de cálculos numéricos en la computación clásica consiste principalmente en resolver sistemas de ecuaciones lineales. Esto es especialmente cierto en el campo del aprendizaje automático, donde la mayor parte del costo de cálculo se destina en calcular la inversa de grandes matrices.

Afortunadamente, existe un algoritmo cuántico que nos permite resolver, de manera aproximada, el sistema exponencialmente más rápido que un equipo clásico. Esto abre la puerta a grandes aceleraciones en cada problema que necesita la solución para los sistemas de ecuaciones lineales.

Las soluciones a los problemas de estas áreas ayudarán a abordar la crisis energética, el cambio climático, la escasez alimentaria y el diagnóstico personal y médico preciso.

## <a name="quantum-inspired-computing"></a>Computación de inspiración cuántica

Los algoritmos de inspiración cuántica se implementan con software clásico, pero usan principios de la cuántica para aumentar la velocidad y la precisión.

Los algoritmos de inspiración cuántica se aplican a la investigación médica. Por ejemplo, para mejorar la precisión de las imágenes de resonancia magnética (RM). La computación de inspiración cuántica se utiliza para optimizar la configuración de las máquinas de RM para la identificación de enfermedades específicas.

## <a name="next-steps"></a>Pasos siguientes

* [¿Por qué debería aprender computación cuántica?](xref:microsoft.quantum.overview.why)
* [Comience con el Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
