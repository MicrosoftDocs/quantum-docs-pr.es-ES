---
title: Introducción a la biblioteca de química cuántica
description: Obtenga información sobre la biblioteca de química cuántica de Microsoft y cómo se usa para simular problemas de estructura electrónica en equipos cuánticos.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: 4268eafa5e53c0a026d179503ac6db88652a8f90
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907331"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Introducción a la biblioteca de química cuántica

La simulación de sistemas físicos juega un papel primordial en la computación cuántica.  Esto se debe a que la dinámica cuántica se considera inextricable para realizar simulaciones en equipos cuánticos, lo que significa que la complejidad de la simulación del sistema aumenta exponencialmente con el tamaño del sistema cuántico en cuestión.  La simulación de problemas en química y ciencia de materiales sigue siendo posiblemente la aplicación más evocadora de la computación cuántica y nos permitirá probar mecanismos de reacción química que hasta la fecha estaban fuera de nuestra capacidad de medir o simular.  También nos permitirá simular materiales electrónicos correlacionados, como superconductores a alta temperatura. La lista de aplicaciones en este espacio es inmensa.

El objetivo de esta documentación es proporcionar una introducción concisa a la simulación de problemas de estructura electrónica en equipos cuánticos para ayudar al lector a comprender el rol que muchos aspectos de la biblioteca de simulación de funciones de Hamilton desempeñan en el espacio.  Comenzamos con una breve introducción a la mecánica cuántica y luego continuaremos con el análisis de cómo se modelan los sistemas electrónicos en ella.  A continuación, veremos cómo se puede emular dicha dinámica cuántica con un equipo cuántico.  Tras ello, se tratarán dos métodos que se usan para compilar la dinámica cuántica en secuencias de puertas elementales: Las descomposiciones de Trotter-Suzuki y la qubitización.
