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
# <a name="quantum-chemistry-examples"></a>Ejemplos de química cuántica

En los conceptos de química cuántica, creamos manualmente ejemplos de funciones de Hamilton fermiónicas. Ahora combinamos los algoritmos de simulación de química descritos en [Simulación de dinámica de funciones de Hamilton](xref:microsoft.quantum.libraries.standard.algorithms) con la [estimación de la fase cuántica](xref:microsoft.quantum.libraries.characterization) en la biblioteca de Canon. Esta combinación nos permite obtener estimaciones de niveles de energía en la molécula representada, que es una de las aplicaciones clave de la química cuántica en un equipo cuántico. 

En lugar de especificar los términos de la función de Hamilton de uno en uno, también trabajamos en algunos ejemplos que nos permiten realizar experimentos de química cuántica a escala. Comenzamos con ejemplos que cargan una función de Hamilton de química codificada en el [esquema de Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

En el caso de las moléculas que son demasiado grandes para simular en el [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), todavía se pueden llevar a cabo operaciones científicas interesantes. Por ejemplo, los costos de recursos de la realización de simulaciones de química de gran envergadura se pueden seguir evaluando con el [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro).

Ahora ilustraremos algunas aplicaciones interesantes de la biblioteca de simulación de química con algunos de los ejemplos proporcionados.
