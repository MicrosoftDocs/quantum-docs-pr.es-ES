---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: 579300d4efb9e22cb671fbb4bce0a6f72dd0e2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853415"
---
# <a name="dumpmachine-function"></a>DumpMachine función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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