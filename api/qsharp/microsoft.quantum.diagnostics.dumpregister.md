---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 835c7a9edb22b4be630ebfc04587c12b3ff668b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829224"
---
# <a name="dumpregister-function"></a>DumpRegister función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vuelca el estado de la máquina de destino actual asociado a la qubits especificada.

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="location--t"></a>Ubicación: ' t

Proporciona información sobre dónde generar el volcado del estado.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Lista de qubits que se van a notificar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

Ninguno.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="remarks"></a>Observaciones

Este método permite volcar la información asociada con el estado de la qubits especificada en un archivo o en otra ubicación.
La información real generada y la semántica de `location` son específicas de cada equipo de destino. Sin embargo, proporcionar una tupla vacía como ubicación ( `()` ) normalmente significa generar la salida en la consola.

En el caso del simulador de estado completo local distribuido como parte del kit de desarrollo de Quantum, este método espera una cadena con la ruta de acceso a un archivo en el que escribirá el estado del qubits determinado (es decir, la función Wave del subsistema correspondiente) como una matriz unidimensional de números complejos, en la que cada elemento representa las amplitudes de la probabilidad de medir el
Si el qubits determinado está inscrito con algún otro qubit y su estado no se puede separar, simplemente informa de que el qubits está inscrito.