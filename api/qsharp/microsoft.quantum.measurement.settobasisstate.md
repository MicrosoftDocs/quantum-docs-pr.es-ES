---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operación SetToBasisState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854619"
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