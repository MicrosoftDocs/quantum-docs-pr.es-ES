---
title: Técnicas de desarrollo cuántico
description: Conozca los aspectos básicos del desarrollo de programas de Q#, el trabajo con operaciones, funciones, variables y qubits, y la creación de un programa cuántico simple.
keywords: No agregue ni edite palabras clave sin consultar a su responsable de SEO Champ.
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: e5b7fbde18afbc0333d89f70c5e4596848e30f4f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907722"
---
# <a name="quantum-development-techniques"></a>Técnicas de desarrollo cuántico

En esta sección de la documentación se ofrecen detalles de los conceptos más importantes usados para crear programas cuánticos en Q#, así como para interactuar con ellos desde aplicaciones clásicas.
Damos por supuesto *cierto* conocimiento de los conceptos de computación cuántica, como los que se describen en el artículo acerca de los [conceptos de computación cuántica](xref:microsoft.quantum.concepts.intro), pero no es preciso ser un experto en computación cuántica para sacar gran partido de estas secciones.

Su contenido es el siguiente.

- En [Introducción a los programas en Q#](xref:microsoft.quantum.techniques.file-structure) se proporciona información general sobre el propósito y la funcionalidad del lenguaje de programación Q#. 
    En concreto, se aclara que Q# *no* es un lenguaje que simplemente sirve para simular la mecánica cuántica (aunque indudablemente nuestro simulador de estado completo ofrece esa funcionalidad). 
    En su lugar, Q# se diseñó pensando en el futuro y sus programas describen la forma en que un equipo de control clásico *interactúa* con qubits. 

- En [Operaciones y funciones](xref:microsoft.quantum.techniques.opsandfunctions) se proporcionan detalles de los dos tipos a los que se puede llamar del lenguaje Q#: *operaciones*, que incluyen la acción en sistemas de qubits y cuántico; y *funciones*, que funcionan estrictamente con información clásica. 
    Si la información clásica y la cuántica no funcionaran en tándem, sería imposible acceder a la informática cuántica. 
    En esta sección se describe cómo definir y usar estos tipos a los que se puede llamar en el flujo de control de un programa en Q#.

- En [Variables locales](xref:microsoft.quantum.techniques.local-variables) se describe el rol de las variables dentro de los programas en Q# y cómo sacarles provecho de forma eficaz. 
    En concreto, aprenderá no solo en qué se diferencian las variables inmutables y las mutables, sino también cómo asignarlas y reasignarlas.

- En [Uso de qubits](xref:microsoft.quantum.techniques.qubits) se describen las características de Q# que puede usar para trabajar tanto con qubits individuales como con sistemas de qubits. 
    En concreto, eso conlleva su asignación, la realización de operaciones en ellos y, en último término, su medición. 
    Además, aprenderá algunas técnicas útiles de flujo de control.

- En [Reunir todo](xref:microsoft.quantum.techniques.puttingittogether), sacará provecho de las técnicas de las secciones anteriores para crear un programa que realice **teleportabilidad cuántica**: usar dos bits clásicos para "teletransportar" el estado completo de un qubit a otro.

- En [Ir más allá](xref:microsoft.quantum.techniques.going-further) se presentan técnicas avanzadas que pueden resultar útiles a la hora de pasar a una programación cuántica más compleja. 
    En concreto, se explica el uso de operaciones y funciones *con parámetros de tipo* en Q #, lo que permiten un flujo de control de orden superior independiente de los tipos concretos de su entrada y salida, así como *pedir prestados* qubits. 
    La diferencia entre esto último y la asignación básica de qubits es que las operaciones de Q# pueden usar qubits "sucios" (que no se han inicializado necesariamente en un estado conocido) como ayuda para los cálculos.

- En [Pruebas y depuración](xref:microsoft.quantum.techniques.testing-and-debugging), se muestran con todo lujo de detalles, algunas técnicas para asegurarse de que el código funciona como debería. 
    Dada la opacidad general de la información acerca de lo cuántico, la depuración de un programa cuántico puede requerir técnicas especializadas. 
    Afortunadamente, Q# admite muchas de las técnicas de depuración clásicas a las que están acostumbrados los programadores, así como otras que son específicas del mundo cuántico. Entre ellas se incluye la creación y ejecución de pruebas unitarias en Q#, la inserción de *aserciones* en los valores y probabilidades del código y las funciones `Dump` cuyo resultado es el estado de la máquina de destino. 
    Estas últimas se pueden usar junto con el simulador de estado completo para depurar ciertas partes de los cálculos, ya que se sortean algunas de las limitaciones del entorno cuántico (por ejemplo, el teorema de no clonación).


![Cuanto](~/media/mobius_strip_preview.png)
