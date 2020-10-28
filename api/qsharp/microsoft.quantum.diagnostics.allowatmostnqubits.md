---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Operación AllowAtMostNQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727365"
---
# <a name="allowatmostnqubits-operation"></a>Operación AllowAtMostNQubits

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Configura [](https://nuget.org/packages/)


Entre una llamada a esta operación y su método contiguo, se declara que como máximo un número determinado de qubits adicionales se asignan con instrucciones using.

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Número máximo de qubits que se pueden asignar.


### <a name="message--string"></a>Message: [cadena](xref:microsoft.quantum.lang-ref.string)

Mensaje que se va a mostrar cuando se produzca un error.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Esta operación se puede reemplazar por una no operativa en destinos que no la admitan.