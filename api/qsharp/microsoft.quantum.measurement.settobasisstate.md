---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operación SetToBasisState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194158"
---
# <a name="settobasisstate-operation"></a>Operación SetToBasisState

Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Establece un qubit en un estado de base de cálculo determinado midiendo el qubit y aplicando un volteo de bits si es necesario.

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="desired--__invalidresult__"></a>deseado: __no <Result> válido__

El estado de base en el que debe establecerse el valor de qubit.


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit cuyo estado se va a establecer.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Como invariable de esta operación, al llamar a `M(q)` inmediatamente después de, `SetToBasisState(result, q)` se devolverá `result` .