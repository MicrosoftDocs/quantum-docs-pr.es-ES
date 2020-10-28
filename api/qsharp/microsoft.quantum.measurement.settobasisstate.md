---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operación SetToBasisState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733604"
---
# <a name="settobasisstate-operation"></a>Operación SetToBasisState

Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Configura [](https://nuget.org/packages/)


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