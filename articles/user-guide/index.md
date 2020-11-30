---
title: Guía de usuario de Q#
description: Información general sobre el propósito y el contenido del manual del usuario
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231764"
---
# <a name="the-no-locq-user-guide"></a>Guía de usuario de Q#

Le damos la bienvenida al manual del usuario de Q#. 

En los distintos temas de esta guía, se presentan algunos de los aspectos básicos para desarrollar programas cuánticos con Q#.

Consulte la [guía del lenguaje de Q#](xref:microsoft.quantum.qsharp.index) para obtener la especificación y documentación completa del lenguaje de programación cuántica Q#. 

## <a name="user-guide-contents"></a>Contenido del manual del usuario

- [Programas de Q#](xref:microsoft.quantum.guide.programs): introducción rápida a los programas cuánticos de Q#. 

- [Maneras de ejecutar un programa de Q#](xref:microsoft.quantum.guide.host-programs): describe cómo se ejecuta un programa de Q# y proporciona información general sobre las distintas formas en que se puede llamar al programa; por ejemplo, desde la línea de comandos, en cuadernos en Q# de Jupyter Notebook o desde un programa de host clásico escrito en Python o en un lenguaje .NET.

- [Prueba y depuración](xref:microsoft.quantum.guide.testingdebugging): detalla algunas técnicas que se usan para asegurarse de que el código hace lo que se supone que debe hacer. 
    Dada la opacidad general de la información acerca de lo cuántico, la depuración de un programa cuántico puede requerir técnicas especializadas. 
    Afortunadamente, Q# admite muchas de las técnicas de depuración clásicas que los programadores conocen, así como otras que son específicas de la computación cuántica. Entre ellas, se incluye la creación y ejecución de pruebas unitarias en Q#, la inserción de *aserciones* en los valores y las probabilidades del código, y las funciones `Dump`, cuyo resultado es el estado de la máquina de destino. 
    Estas últimas se pueden usar junto con el simulador de estado completo para depurar ciertas partes de los cálculos, ya que se sortean algunas de las limitaciones de la computación cuántica, por ejemplo, el [teorema de no clonación](xref:microsoft.quantum.concepts.pauli).

### <a name="quantum-simulators-and-resource-estimators"></a>Simuladores cuánticos y calculadoras de recursos

- [Simuladores cuánticos y aplicaciones host](xref:microsoft.quantum.machines): introducción a los diferentes simuladores disponibles, y cómo trabajan juntos los programas host y las máquinas de destino para ejecutar programas de Q#.

- [Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): equipo de destino que simula el estado cuántico completo. Resulta útil para ejecutar o depurar programas de menor escala (menos de un par de docenas de cúbits).

- [Calculadora de recursos](xref:microsoft.quantum.machines.resources-estimator): calcula los recursos necesarios para ejecutar una instancia dada de una operación de Q# en un equipo cuántico.

- [Simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro): ejecuta un programa cuántico sin simular realmente el estado de un equipo cuántico y, por consiguiente, puede ejecutar programas cuánticos que usan miles de cúbits. Resulta útil para depurar código clásico en un programa cuántico, así como para calcular los recursos necesarios.

- [Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulador cuántico con un uso específico que se puede usar con millones de cúbits, pero solo para aquellos programas que tienen un conjunto restringido de operaciones cuánticas (X, CNOT y X con controles múltiples).

### <a name="quick-reference-pages"></a>Páginas de referencia rápida

- [Comandos magic de IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referencia rápida de los comandos magic de IQ# en cuadernos en Q# de Jupyter Notebook.
