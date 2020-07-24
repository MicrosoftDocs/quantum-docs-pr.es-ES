---
title: Simuladores cuánticos y programas de Q#
description: Describe los simuladores cuánticos disponibles como máquinas de destino para los programas de Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: c81226ba3e50b65cb1012e885866bd6fcc3764d7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871168"
---
# <a name="quantum-simulators"></a>Simuladores cuánticos

Los simuladores cuánticos son programas de software que se ejecutan en equipos clásicos y actúan como *máquina de destino* para programas de Q#. Permiten ejecutar y probar programas cuánticos en un entorno que predice cómo reaccionarán los cúbits a las distintas operaciones. En este artículo se describe qué simuladores cuánticos se incluyen con el kit de desarrollo de Microsoft Quantum (QDK) y diferentes maneras de pasar un programa de Q# a los simuladores cuánticos, por ejemplo, desde la línea de comandos o mediante código de controlador escrito en un lenguaje clásico.  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a>Simuladores cuánticos del kit de desarrollo de Microsoft Quantum (QDK)

El simulador cuántico es responsable de proporcionar las implementaciones de las primitivas cuánticas de un algoritmo. Esto incluye operaciones primitivas como `H`, `CNOT` y `Measure`, así como el seguimiento y la administración de cúbits. El QDK incluye distintas clases de simuladores cuánticos que representan modelos de ejecución diferentes para el mismo algoritmo cuántico. 


Cada tipo de simulador cuántico puede ofrecer distintas implementaciones de estas operaciones primitivas. Por ejemplo, para ejecutar el algoritmo cuántico, el [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator) realiza una simulación completa del [vector de estado cuántico](xref:microsoft.quantum.glossary#quantum-state), mientras que el [simulador de seguimiento de equipos cuánticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro) no tiene en cuenta el estado cuántico real. En su lugar, hace un seguimiento del uso de puertas, cúbits y otros recursos para el algoritmo.

### <a name="quantum-machine-classes"></a>Clases de máquinas cuánticas

En el futuro, el QDK definirá más clases de máquinas cuánticas para admitir otros tipos de simulación y la ejecución en hardware cuántico. Permitir que el algoritmo permanezca constante mientras varía la implementación de la máquina subyacente permite facilitar la prueba y depuración de un algoritmo en la simulación y, después, ejecutarlo en hardware real con la confianza de que el algoritmo no haya cambiado.

El QDK incluye varias clases de máquinas cuánticas, todas ellas definidas en el espacio de nombres `Microsoft.Quantum.Simulation.Simulators`.

|Simulador |Clase|Descripción|
|-----|------|---|
|[Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | Ejecuta y depura algoritmos cuánticos, y está limitado a 30 cúbits aproximadamente. |
|[Estimador de recursos sencillo](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | Realiza un análisis general de los recursos necesarios para ejecutar un algoritmo cuántico y admite miles de cúbits.|
|[Simulador de seguimiento de equipos cuánticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |Realiza análisis avanzados del consumo de recursos de todo el grafo de llamada del algoritmo y admite miles de cúbits.|
|[Simulador de Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |Simula algoritmos cuánticos que se limitan a operaciones cuánticas `X`, `CNOT` y `X` de control múltiple, y admite millones de cúbits. |

## <a name="invoking-the-quantum-simulator"></a>Invocación del simulador cuántico

En [Maneras de ejecutar un programa de Q#](xref:microsoft.quantum.guide.host-programs), se muestran tres maneras de pasar código de Q# al simulador cuántico: 

* Mediante la línea de comandos
* Mediante un programa host de Python
* Mediante un programa host de C#

Las máquinas cuánticas son instancias de las clases .NET normales, por lo que se crean mediante la invocación de su constructor, del mismo modo que cualquier clase .NET. La forma de hacerlo depende de cómo ejecute el programa de Q#.

## <a name="next-steps"></a>Pasos siguientes

* Para más información sobre cómo invocar las máquinas de destino para los programas de Q# en entornos diferentes, consulte [Maneras de ejecutar un programa de Q#](xref:microsoft.quantum.guide.host-programs).
