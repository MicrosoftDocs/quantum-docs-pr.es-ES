---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727287"
---
# <a name="dumpmachine-function"></a>DumpMachine función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Configura [](https://nuget.org/packages/)


Vuelca el estado actual del equipo de destino.

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="location--t"></a>Ubicación: ' t

Proporciona información sobre dónde generar el volcado del equipo.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

Ninguno.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="remarks"></a>Observaciones

Este método permite volcar información sobre el estado actual del equipo de destino en un archivo o en otra ubicación.
La información real generada y la semántica de `location` son específicas de cada equipo de destino. Sin embargo, proporcionar una tupla vacía como ubicación ( `()` ) o simplemente omitir el `location` parámetro significa que se va a generar la salida en la consola.

Para el simulador de estado completo local distribuido como parte del kit de desarrollo de Quantum, este método espera una cadena con la ruta de acceso a un archivo en el que escribirá la función de onda como una matriz unidimensional de números complejos, en la que cada elemento representa las amplitudes de la probabilidad de medir el estado correspondiente.