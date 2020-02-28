---
title: 'Broombridge: esquema de química de Quantum'
description: Información general sobre el esquema de química Broombridge Quantum, que se usa para modelar problemas de química del mundo real con el Microsoft Quantum Development Kit.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: a746b63055bb1b2c1168b89993a7459ca9597f86
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907824"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Esquema de química Broombridge Quantum # 

Un potente software de química informática, como [NWChem](http://www.nwchem-sw.org/) , permite modelar una amplia gama de problemas de química del mundo real. Con el fin de acceder a los modelos moleculares de NWChem con la biblioteca de química de Microsoft Quantum, usamos un esquema basado en [YAML](https://en.wikipedia.org/wiki/YAML)al que llamamos **Broombridge**. El nombre se eligió en referencia [a un punto de referencia que](https://en.wikipedia.org/wiki/Broom_Bridge) en algunos círculos se celebrated como un nacimiento de Hamiltonians. 

[NWChem](https://github.com/nwchemgit/nwchem) es un proyecto de código abierto con licencia de la licencia de la comunidad educativa (ECL) 2,0. Broombridge es un esquema de código abierto que se especifica [aquí](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) y que incluye una [definición](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) que sigue a [RFC 2119](https://tools.ietf.org/html/rfc2119) y el [script validador](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) con licencia de MIT. 

Basado en YAML, Broombridge es una forma estructurada, legible y modificable que representa los problemas de la estructura electrónica. En concreto, se pueden representar los datos siguientes: 
- Fermionic Hamiltonians se puede representar con enteros de uno y dos electrones. 
- Los Estados de suelo y emocionados se pueden presentar mediante secuencias de creación.
- Se pueden especificar los límites superior e inferior de los niveles de energía.

El formato de los datos se puede generar a partir de NWChem con facilidad de uso sencillo: hay disponible una variedad de métodos que abarcan desde una instalación completa de NWChem para ejecutar Barajas de química, como los que se proporcionan [aquí](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) y Broombridge de salida como parte de la ejecución, a través de una imagen de Docker de NWChem que también se puede usar para generar Broombridge desde Barajas de química. Por último, un método visual para empezar a trabajar con la Química computacional rápidamente sin tener que instalar ningún software de química lo proporciona la interfaz de [flechas emsl](https://arrows.emsl.pnnl.gov/api/qsharp_chem) a NWChem. 

En un nivel alto, la interreproducción entre NWChem y el Microsoft Quantum Development Kit se puede visualizar como se indica a continuación: ![pila de química](~/media/broombridge.png) el cuadro sombreado azul representa el esquema Broombridge, los distintos cuadros sombreados en gris representan otras representaciones de datos internos que se eligieron para representar y procesar algoritmos Quantum para la Química computacional basada en problemas de química del mundo real. 

[Aquí](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)se proporcionan varias representaciones químicas definidas mediante el esquema Broombridge.
