---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: a6d29dbf0525077fd804563f85f189740fdc0429
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727274"
---
# <a name="dumpregister-function"></a>DumpRegister función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Configura [](https://nuget.org/packages/)


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