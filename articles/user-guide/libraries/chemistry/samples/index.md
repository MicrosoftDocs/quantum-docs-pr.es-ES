---
title: Aplicaciones de ejemplo de química cuántica
description: Explore las aplicaciones de ejemplo de la biblioteca de química cuántica de Microsoft.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: conceptual
uid: microsoft.quantum.chemistry.examples
no-loc:
- Q#
- $$v
ms.openlocfilehash: b2a8740f9c94ca733e24012aaf5c80b15b731c2e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858916"
---
# <a name="quantum-chemistry-examples"></a>Ejemplos de química cuántica

En los conceptos de química cuántica, creamos manualmente ejemplos de funciones de Hamilton fermiónicas. Ahora combinamos los algoritmos de simulación de química descritos en [Simulación de dinámica de funciones de Hamilton](xref:microsoft.quantum.libraries.standard.algorithms) con la [estimación de la fase cuántica](xref:microsoft.quantum.libraries.characterization) en la biblioteca de Canon. Esta combinación nos permite obtener estimaciones de niveles de energía en la molécula representada, que es una de las aplicaciones clave de la química cuántica en un equipo cuántico. 

En lugar de especificar los términos de la función de Hamilton de uno en uno, también trabajamos en algunos ejemplos que nos permiten realizar experimentos de química cuántica a escala. Comenzamos con ejemplos que cargan una función de Hamilton de química codificada en el [esquema de Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

En el caso de las moléculas que son demasiado grandes para simular en el [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), todavía se pueden llevar a cabo operaciones científicas interesantes. Por ejemplo, los costos de recursos de la realización de simulaciones de química de gran envergadura se pueden seguir evaluando con el [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro).

Ahora ilustraremos algunas aplicaciones interesantes de la biblioteca de simulación de química con algunos de los ejemplos proporcionados.
