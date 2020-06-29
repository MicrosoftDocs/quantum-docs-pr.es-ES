---
title: Manual del usuario de Q#
description: Información general sobre el propósito y el contenido del manual del usuario
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: c5611f3e2907791f2dfc1644be0a45515d50dfd7
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415377"
---
# <a name="the-q-user-guide"></a>Manual del usuario de Q#

Bienvenido al manual del usuario de Q# 

En los temas de esta guía se detallan los conceptos básicos del lenguaje Q#, así como toda la información necesaria para escribir programas cuánticos.

## <a name="user-guide-contents"></a>Contenido del manual del usuario

- [Conceptos básicos de Q#](xref:microsoft.quantum.guide.basics): introducción a la finalidad y funcionalidad del lenguaje de programación Q#. 

### <a name="q-language"></a>Lenguaje Q#

- [Tipos en Q#](xref:microsoft.quantum.guide.types): describe el modelo de tipos de Q# y la sintaxis necesaria para especificar tipos y trabajar con ellos.

- [Expresiones de tipo](xref:microsoft.quantum.guide.expressions): detalla cómo especificar los valores de cada tipo en Q# y cómo hacer referencia a ellos, combinarlos y operar con ellos. 

### <a name="using-q"></a>Uso de Q#

- [Estructura de archivos de Q#](xref:microsoft.quantum.guide.filestructure): describe la estructura y sintaxis de un archivo `*.qs` de Q#.

- [Operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions): detallada los dos tipos invocables del lenguaje Q#: *operaciones*, incluidas acciones en los registros de cúbits, y *funciones*, que funcionan estrictamente con información clásica. 
    Aquí se ve cómo definir y llamar a ambos tipo, los que incluye las versiones controlada y de adjoint de las operaciones cuánticas.

- [Variables](xref:microsoft.quantum.guide.variables): describe el papel que juegan las variables en los programas de Q# y cómo usarlas de forma eficaz. 
    Por ejemplo, puede encontrar información sobre los ámbitos de enlace, así como la diferencia entre las variables inmutables y mutables, y cómo asignarlas o reasignarlas.

- [Trabajo con cúbits](xref:microsoft.quantum.guide.qubits): describe las características de Q# que se usan para trabajar con cúbits individuales y sistemas de cúbits, en concreto, asignarlos, ejecutar operaciones en ellos y medirlos. 

- [Flujo de control](xref:microsoft.quantum.guide.controlflow): detalla los patrones del flujo de control de programación disponibles en Q#, incluidas numerosas técnicas estándar (ejecución condicional, bucles for, bucles while), así como el patrón "repetir hasta obtener un resultado correcto", específico de la computación cuántica.

- [Prueba y depuración](xref:microsoft.quantum.guide.testingdebugging): detalla algunas técnicas que se usan para asegurarse de que el código hace lo que se supone que debe hacer. 
    Dada la opacidad general de la información acerca de lo cuántico, la depuración de un programa cuántico puede requerir técnicas especializadas. 
    Afortunadamente, Q# admite muchas de las técnicas de depuración clásicas que los programadores conocen, así como otras que son específicas de la computación cuántica. Entre ellas, se incluye la creación y ejecución de pruebas unitarias en Q#, la inserción de *aserciones* en los valores y probabilidades del código y las funciones `Dump` cuyo resultado es el estado de la máquina de destino. 
    Estas últimas se pueden usar junto con el simulador de estado completo para depurar ciertas partes de los cálculos, ya que se sortean algunas de las limitaciones de la computación cuántica, por ejemplo, el [teorema de no clonación](xref:microsoft.quantum.concepts.pauli).

### <a name="quantum-simulators-and-resource-estimators"></a>Simuladores cuánticos y calculadoras de recursos

- [Simuladores cuánticos y aplicaciones host](xref:microsoft.quantum.machines): introducción a los diferentes simuladores disponibles, así como el modelo de ejecución general entre los programas host y las máquinas de destino.

- [Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): equipo de destino que simula el estado cuántico completo. Resulta útil para ejecutar o depurar programas de menor escala (menos de un par de docenas de cúbits).

- [Calculadora de recursos](xref:microsoft.quantum.machines.resources-estimator): calcula los recursos necesarios para ejecutar una instancia dada de una operación de Q# en un equipo cuántico.

- [Simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro): ejecuta un programa cuántico sin simular realmente el estado de un equipo cuántico y, por consiguiente, puede ejecutar programas cuánticos que usan millares de cúbits. Resulta útil para depurar código clásico en un programa cuántico, así como para calcular los recursos necesarios.

- [Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulador cuántico con un uso específico que se puede usar con millones de cúbits, pero solo para aquellos programas que tienen un conjunto restringido de operaciones cuánticas (X, CNOT y X con controles múltiples).

### <a name="quick-reference-pages"></a>Páginas de referencia rápida

- [Comandos magic de IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referencia rápida de comandos magic de IQ # en cuadernos de Jupyter Notebook de Q#.
