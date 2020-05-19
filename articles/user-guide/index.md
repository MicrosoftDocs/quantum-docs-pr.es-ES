---
title: Manual del usuario de Q#
description: Información general sobre el propósito y el contenido del manual del usuario
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430618"
---
# <a name="the-q-user-guide"></a>Manual del usuario de Q#

Bienvenido al manual del usuario de Q# 

En este manual se detallan los conceptos básicos del lenguaje Q#, así como toda la información necesaria para escribir programas de Quantum.

## <a name="user-guide-contents"></a>Contenido del manual del usuario

- [Conceptos básicos de Q#](xref:microsoft.quantum.guide.basics): información general que introduce la finalidad y funcionalidad del lenguaje de programación Q#. 

### <a name="q-language"></a>Lenguaje Q#

- [Tipos en Q#](xref:microsoft.quantum.guide.types): compone el modelo de tipos de Q# y describe la sintaxis necesaria para especificar y trabajar con tipos.

- [Expresiones de tipo](xref:microsoft.quantum.guide.expressions): detalla cómo especificar, hacer referencia, combinar y operar en valores de cada tipo en Q#. 

### <a name="using-q"></a>Uso de Q#

- [Estructura de archivos de Q#](xref:microsoft.quantum.guide.filestructure): describe la estructura y sintaxis de un archivo `*.qs` de Q#.

- [Operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions): se proporcionan detalles de los dos tipos a los que se puede llamar del lenguaje Q#: *operaciones*, que incluyen la realización de acciones en los registros de cubits, y *funciones*, que funcionan estrictamente con información clásica. 
    Aquí se ve cómo definir y llamar a ambos tipo, los que incluye las versiones controlada y de adjoint de las operaciones cuánticas.

- [Variables](xref:microsoft.quantum.guide.variables): describe el rol de las variables en los programas de Q# y cómo usarlas de forma eficaz. 
    Por ejemplo, puede encontrar información sobre los ámbitos de enlace, así como la diferencia entre las variables inmutables y mutables, y cómo asignarlas o volver a asignarlas.

- [Uso de cubits](xref:microsoft.quantum.guide.qubits): describe las características de Q# que se usan para trabajar tanto con cubits individuales como con sistemas de cubits. 
    En concreto, eso conlleva su asignación, la realización de operaciones en ellos y, en último término, su medición. 

- [Flujo de control](xref:microsoft.quantum.guide.controlflow): detalla los patrones del flujo de control de programación disponibles en Q#, lo que incluye muchas técnicas estándar (ejecución condicional, bucles for, bucles while, etc.), así como el patrón "Repeat-Until-Success" específico de Quantum.

- [Pruebas y depuración](xref:microsoft.quantum.guide.testingdebugging): detalla algunas técnicas que se usan para asegurarse de que el código hace lo que se supone que debe hacer. 
    Dada la opacidad general de la información acerca de lo cuántico, la depuración de un programa cuántico puede requerir técnicas especializadas. 
    Afortunadamente, Q# admite muchas de las técnicas de depuración clásicas a las que están acostumbrados los programadores, así como otras que son específicas del mundo cuántico. Entre ellas se incluye la creación y ejecución de pruebas unitarias en Q#, la inserción de *aserciones* en los valores y probabilidades del código y las funciones `Dump` cuyo resultado es el estado de la máquina de destino. 
    Estas últimas se pueden usar junto con el simulador de estado completo para depurar ciertas partes de los cálculos, ya que se sortean algunas de las limitaciones del entorno cuántico (por ejemplo, el teorema de no clonación).

### <a name="quantum-simulators-and-resource-estimators"></a>Simuladores cuánticos y calculadoras de recursos

- [Simuladores cuánticos y aplicaciones host](xref:microsoft.quantum.machines): información general de los diferentes simuladores disponibles, así como el modelo de ejecución general entre el programa host y las máquinas de destino.

- [Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): el equipo de destino que simula el estado cuántico completo. Resulta útil para ejecutar o depurar programas de menor escala (menos de un par de docenas de cubits)

- [Calculadora de recursos](xref:microsoft.quantum.machines.resources-estimator): calcula los recursos necesarios para ejecutar una instancia dada de una operación de Q# en un equipo cuántico.

- [Simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro): ejecuta un programa cuántico sin simular realmente el estado de un equipo cuántico y, por consiguiente, puede ejecutar programas cuánticos que usan millares de cubits. Resulta útil para depurar código clásico en un programa cuántico, así como para calcular los recursos necesarios.

- [Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): un simulador cuántico con un uso especial que se puede usar con millones de cubits, pero solo para aquellos programas que tienen un conjunto restringido de operaciones cuánticas (a saber, X, CNOT y X con controles múltiples).

### <a name="quick-reference-pages"></a>Páginas de referencia rápida

- [Comandos magic de IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referencia rápida de comandos magic de IQ # en cuadernos de Jupyter Notebook de Q#.
