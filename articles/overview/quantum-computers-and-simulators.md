---
title: Simuladores y equipos cuánticos
description: Obtenga información sobre el hardware cuántico, simuladores cuánticos y cómo funcionan las operaciones cuánticas.
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8691838b2d6c54baa40042245eee8c901a7ca965
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835016"
---
# <a name="quantum-computers-and-quantum-simulators"></a>Simuladores y equipos cuánticos

Los equipos cuánticos aún están en desarrollo. El hardware y el mantenimiento son costosos, y la mayoría de los sistemas se encuentran en universidades y laboratorios de investigación. Sin embargo, la tecnología sigue avanzando y ya hay un acceso público limitado a algunos sistemas.

Los simuladores cuánticos son programas de software que se ejecutan en equipos clásicos y permiten ejecutar y probar programas cuánticos en un entorno que predice cómo reaccionarán los cúbits a las diferentes operaciones.

## <a name="quantum-hardware"></a>Hardware cuántico

Un equipo cuántico tiene tres partes principales: un área que hospeda los cúbits, un método para transferir señales a los cúbits y un equipo clásico para ejecutar un programa y enviar instrucciones.

- El material cuántico usado para los cúbits es frágil y extremadamente sensible a las interferencias del entorno. En algunos métodos de almacenamiento de cúbits, la unidad que hospeda los cúbits se mantiene a una temperatura justo por encima del cero absoluto para maximizar su coherencia. Otros tipos de alojamiento de cúbits usan una cámara de vacío para ayudar a minimizar las vibraciones y estabilizar los cúbits.  
- Las señales se pueden enviar a los cúbits con diversos métodos, entre ellos, microondas, láser y tensión.

Los equipos cuánticos se enfrentan a numerosos desafíos para funcionar correctamente. La corrección de errores en los equipos cuánticos supone un problema importante, y el escalado vertical (agregar más cúbits) aumenta la tasa de errores. Debido a estas limitaciones, los equipos cuánticos de escritorio aún son cosa del futuro, pero un equipo cuántico de laboratorio que sea viable comercialmente ya está más cerca.

## <a name="quantum-simulators"></a>Simuladores cuánticos

Los simuladores cuánticos que se ejecutan en equipos clásicos permiten simular el procesamiento de algoritmos cuánticos en un sistema cuántico.  El kit de desarrollo de Microsoft Quantum (QDK) incluye un simulador de vectores de estado completo junto con otros simuladores cuánticos especializados.

## <a name="topological-qubit"></a>Cúbit topológico

Microsoft está desarrollando un equipo cuántico basado en cúbits topológicos. Un cúbit topológico se verá menos afectado por los cambios en su entorno, por lo que se reduce el grado de corrección de errores externos necesario.

La característica de cúbits topológicos aumentó la estabilidad y la resistencia al ruido ambiental, lo que significa que se pueden escalar más fácilmente y seguir siendo confiables durante más tiempo.

## <a name="microsoft-and-quantum-hardware-partnerships"></a>Asociados de hardware cuántico de Microsoft

Microsoft se está asociando con los fabricantes de hardware cuántico IonQ, Honeywell y QCI para que los desarrolladores puedan tener acceso a equipos cuánticos en el futuro. Con la plataforma Azure Quantum, los desarrolladores podrán usar el kit de desarrollo de Microsoft Quantum (QDK) y Q# para escribir programas cuánticos y ejecutarlos de forma remota.

## <a name="quantum-computations"></a>Cálculos cuánticos

Realizar cálculos en un equipo cuántico o en un simulador cuántico sigue un proceso básico:

- Acceso a los cúbits
- Inicialización de los cúbits con el estado deseado
- Aplicación de las operaciones para transformar los estados de los cúbits
- Medición de los nuevos estados de los cúbits

La inicialización y transformación de los cúbits se realiza mediante **operaciones cuánticas** (también llamadas puertas cuánticas). Las operaciones cuánticas son similares a las operaciones lógicas de la informática clásica, como AND, OR, NOT y XOR. Una operación puede ser tan básica como cambiar el estado de un cúbit de 1 a 0 o entrelazar un par de cúbits, hasta usar varias operaciones en serie para influir en la probabilidad de que un cúbit superpuesto colapse en una forma o la otra.

> [!NOTE] 
> Las [bibliotecas de Q#](xref:microsoft.quantum.libraries) proporcionan operaciones integradas que definen combinaciones complejas de operaciones cuánticas de nivel inferior. Puede utilizar las operaciones de las bibliotecas para transformar cúbits y crear operaciones más complejas definidas por el usuario.  

La medición del resultado del cálculo nos da una respuesta, pero en el caso de algunos algoritmos cuánticos, no es necesariamente la respuesta correcta. Dado que el resultado de algunos algoritmos cuánticos se basa en la probabilidad configurada por las operaciones cuánticas, estos cálculos se ejecutan varias veces para obtener una distribución de la probabilidad y afinar la precisión de los resultados.  La garantía de que una operación devuelva una respuesta correcta se conoce como comprobación cuántica y es un desafío importante en la computación cuántica.

## <a name="summary"></a>Resumen

La computación cuántica comparte algunos conceptos con la informática clásica, pero incorpora nuevos giros. Estas son algunos de los aspectos clave:

- El hardware cuántico es caro y frágil, por lo que se usan simuladores cuánticos para escribir y probar programas.
- Tanto los equipos clásicos como cuánticos usan operaciones lógicas (o puertas) para preparar los cálculos.
- Los cálculos cuánticos devuelven probabilidades.

Los avances en el hardware y las técnicas cuánticas cambian rápidamente el panorama. Estos son solo algunos de los [desarrollos actuales](https://phys.org/search/?search=quantum+computer&s=0).

## <a name="next-steps"></a>Pasos siguientes

[¿Qué son el QDK y el lenguaje de programación Q#?](xref:microsoft.quantum.overview.q-sharp)
