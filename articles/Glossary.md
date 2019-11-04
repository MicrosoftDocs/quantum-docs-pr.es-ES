---
title: Glosario | Microsoft Docs
description: Glosario de términos de Quantum
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: bfa275b3330ea2c2a541b08f137893b63b6213aa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183631"
---
|Duración|Definición|
|-------------|----------|
|Contiguo|La transposición de conjugada compleja de la operación. En el caso de las operaciones que implementan un operador unitario, el contiguo es el inverso de la operación.|
|Llamadas|Las operaciones y las funciones se conocen colectivamente como *Invocables*.|
|Estándar|Operaciones y funciones definidas en Q # Building sobre la lógica definida en el predicho. La implementación de la biblioteca estándar es independiente con respecto a los equipos de destino.|
|Grupo Clifford|Conjunto de operaciones que ocupan el octants de la esfera Bloch. Entre ellas se incluyen: `X`, `Y`, `Z`, `H` y `S`|
|Regula|Una operación Quantum que toma uno o más qubits como habilitadores para la operación de destino.|
|Notación Dirac|Una representación abreviada del estado de Quantum. Vea la sección [notación de Dirac](xref:microsoft.quantum.concepts.dirac) para obtener más detalles.|
|Vectores propios y vectores propios|Consulte la [sección matriz avanzada](xref:microsoft.quantum.concepts.matrix-advanced) para más información.|
|Par de EPR|También conocido como [Estado de campana](https://en.wikipedia.org/wiki/Bell_state)|
|Calidad|Cómo cambia el estado a lo largo del tiempo. Vea la sección sobre <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials> para obtener un ejemplo. |
|Función|Rutinas puramente clásicas en el lenguaje de preguntas y respuestas|
| <a id="global-phase"></a>Fase global | Dos Estados que son idénticos a un múltiplo de un número complejo $e ^ {i\phi} $ se dice que difieren en una fase global. A diferencia de las fases locales, las fases globales no se pueden observar a través de ninguna medida. Consulte [Pauli Measurements](xref:microsoft.quantum.concepts.pauli) para obtener más información. |
|Medición|Obtener un bit clásico de un qubit (o un conjunto de qubits). Vea la sección [conceptos de qubit](xref:microsoft.quantum.concepts.qubit) para obtener más detalles.|
|Mutable|Variable cuyo valor se puede cambiar una vez creado.|
|Espacio de nombres|Etiqueta para una colección de nombres relacionados (normalmente operaciones, funciones y tipos). Por ejemplo, el espacio de nombres [`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation) etiqueta todos los símbolos definidos en la biblioteca estándar que ayudan a preparar los Estados iniciales.|
|Operación|La unidad básica de ejecución de Quantum en Q #. Es aproximadamente equivalente a una función de C o C++ o Python, o a un método estático en C# o Java.|
|Operador Application|Realización de una operación Quantum. Normalmente, esto aplica una matriz de unitarios al vector de estado actual. Para más información, consulte [Introducción a los conceptos de Quantum](xref:microsoft.quantum.concepts.intro) .|
|Oracle|Subrutina que proporciona información dependiente de datos a un algoritmo Quantum en tiempo de ejecución. Normalmente, el objetivo es proporcionar una superposición de salidas que corresponden a las entradas que están en posición de superposición.   |
|Aplicación parcial|Llamar a una función u operación sin todos los parámetros necesarios. Devuelve un nuevo invocable que solo necesita los parámetros que faltan proporcionados durante una aplicación futura.|
|Operadores Pauli|Las puertas de `X`, `Y` y `Z` Quantum.|
|Preludio|Conjunto de operaciones primitivas y clásicas y funciones definidas por cada equipo de destino individual, en lugar de en el nivel de Q #.|
|Circuito de Quantum|La representación de un programa para un equipo Quantum. Vea la sección <xref:microsoft.quantum.concepts.circuits> para obtener más detalles.|
|Estado de Quantum|Representación de qubits en el sistema. Normalmente, esto se indica como un vector de columna complejo. Para más información, consulte <xref:microsoft.quantum.concepts.vectors>. |
|qubit|Unidad de almacenamiento de Quantum. Vea la sección <xref:microsoft.quantum.concepts.qubit> para obtener más detalles.|
|Repetir hasta éxito|Un algoritmo Quantum que se ejecuta con probabilidad de éxito. En caso de error, la rutina volverá a intentarlo hasta que sea correcta (o se alcance un límite). |
|Pila de software|Conjunto completo de software clásico y Quantum, así como los compiladores, simuladores y tiempos de ejecución necesarios para poner en funcionamiento un equipo Quantum. Vea la sección <xref:microsoft.quantum.concepts.software-stack> para obtener más detalles. |
|Máquina de destino|Un destino de compilación que reduce un programa Quantum abstracto hacia el hardware o la simulación. Esto suele incluir reescrituras para muchos propósitos, incluidos el reemplazo de la puerta, la codificación para la corrección de errores, el diseño geométrico y otros.|
|Organizar|Los tipos separados por comas se agrupan entre paréntesis. |
|Tipo definido por el usuario|Colección de tipos integrados o definidos previamente que se pueden denominar una sola unidad.|

