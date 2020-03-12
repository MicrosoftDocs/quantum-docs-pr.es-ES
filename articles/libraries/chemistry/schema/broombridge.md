---
title: Esquema de química Broombridge Quantum
description: Información general sobre el esquema de química Broombridge Quantum, que se usa para modelar problemas de química del mundo real con el Microsoft Quantum Development Kit.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: 708c4277080c358cb35a49fbf1dde0394d331043
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022535"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Esquema de química Broombridge Quantum # 

Un potente software de química informática, como [NWChem](http://www.nwchem-sw.org/) , permite modelar una amplia gama de problemas de química del mundo real. Con el fin de obtener acceso a los modelos moleculares NWChem con la biblioteca de química de Microsoft Quantum, se usa un esquema basado en [YAML](https://en.wikipedia.org/wiki/YAML)denominado **Broombridge**. El nombre se eligió en referencia [a un punto de referencia que](https://en.wikipedia.org/wiki/Broom_Bridge) en algunos círculos se celebrated como un nacimiento de Hamiltonians. 

[NWChem](https://github.com/nwchemgit/nwchem) es un proyecto de código abierto con licencia de la licencia de la comunidad educativa (ECL) 2,0. El [esquema de química Broombridge Quantum](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)) es un esquema de código abierto que incluye una [definición](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) que sigue a [RFC 2119](https://tools.ietf.org/html/rfc2119) y un [script de validador](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) con licencia de la licencia MIT. 

Basado en YAML, Broombridge es una forma estructurada, legible y modificable que representa los problemas de la estructura electrónica. En concreto, se pueden representar los datos siguientes:
- Fermionic Hamiltonians se puede representar con enteros de uno y dos electrones.
- Los Estados de suelo y emocionados se pueden presentar mediante secuencias de creación.
- Se pueden especificar los límites superior e inferior de los niveles de energía.

Los datos pueden generarse a partir de NWChem mediante varios métodos, como el uso de una instalación completa de NWChem para ejecutar Barajas de química (por ejemplo, las proporcionadas en la [biblioteca de NWChem](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) que generan Broombridge como parte de la ejecución) o una imagen de Docker de NWChem que también se puede usar para generar Broombridge a partir de Barajas de química. Para empezar a trabajar con la Química computacional rápidamente sin tener que instalar ningún software de química, puede usar la interfaz visual para NWChem proporcionado por las [flechas de emsl](https://arrows.emsl.pnnl.gov/api/qsharp_chem).

En un nivel alto, la interreproducción entre NWChem y el Microsoft Quantum Development Kit se puede visualizar como se indica a continuación: ![pila de química](~/media/broombridge.png) el cuadro sombreado azul representa el esquema Broombridge, los distintos cuadros sombreados en gris representan otras representaciones de datos internos que se eligieron para representar y procesar algoritmos Quantum para la Química computacional basada en problemas de química del mundo real.

La carpeta [integral/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) del repositorio de ejemplos del kit de desarrollo de Quantum contiene varias representaciones químicas definidas mediante el esquema Broombridge.
