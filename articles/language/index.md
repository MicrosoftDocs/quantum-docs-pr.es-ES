---
title: El lenguaje de programación Q# | Microsoft Docs
description: El lenguaje de programación Q#
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: 560926f6f3e05c32a935f01ca5107a614e743ee2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442480"
---
# <a name="the-q-programming-language"></a>El lenguaje de programación Q#

## <a name="introduction"></a>Introducción

Un modelo natural de computación cuántica consiste en tratar el equipo cuántico como un coprocesador, similar al que se usa para GPU, FPGA y otros procesadores complementarios.
La lógica de control principal ejecuta código clásico en un equipo "host" clásico.
Cuando es adecuado y necesario, el programa host puede invocar una subrutina que se ejecuta en el procesador complementario.
Cuando se completa la subrutina, el programa host obtiene acceso a los resultados de la subrutina.

Q# (Q-Sharp) es un lenguaje de programación específico del dominio que se usa para expresar algoritmos cuánticos.
Se usa para escribir subrutinas que se ejecutan en un procesador cuántico complementario, bajo el control de un equipo y un programa host clásico.
Hasta que los procesadores cuánticos estén disponibles de forma general, las subrutinas de Q# se ejecutan en un simulador.

Q# proporciona un pequeño conjunto de tipos primitivos y dos maneras (matrices y tuplas) de crear nuevos tipos estructurados.
Admite un modelo de procedimientos básico para escribir programas, con bucles e instrucciones if/then.
Las construcciones de nivel superior en Q# son tipos, operaciones y funciones definidos por el usuario.

En las secciones siguientes se detallan:
- [Modelo de tipos](xref:microsoft.quantum.language.type-model)
- [Expresiones](xref:microsoft.quantum.language.expressions)
- [Instrucciones](xref:microsoft.quantum.language.statements)
- [Estructura de archivos](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a>Convenciones

Estamos trabajando para asegurarnos de que los signos de puntuación comunes se utilicen de forma coherente en todos los casos.
Esperamos que esto facilite el aprendizaje y la lectura de Q#, porque estos signos significarán siempre lo mismo, y el mismo concepto se representa siempre de la misma manera.

Concretamente:

- El punto y coma, `;`, se usa para finalizar una instrucción o una directiva de una sola línea.
  No se usa para ningún otro fin.
- La coma, `,`, se usa para separar los elementos de una secuencia. Se utiliza para literales de tupla, literales de matriz, listas de argumentos, definiciones de tupla y listas de tipos. **En un cambio con respecto a las versiones anteriores, ya no se admite `;` como separador de literales de matriz.**
- Los dos puntos, `:`, se usan para introducir una anotación de tipo. Se utiliza principalmente en signaturas de llamada.
  Como los dos puntos introducen siempre una signatura de tipo, el operador condicional ternario introducido en 0.3 usa una barra vertical, `|`, para separar los valores true y false; por lo tanto, Q# usa `cond ? tval | fval` en lugar de los dos puntos como separador como en C.
  
