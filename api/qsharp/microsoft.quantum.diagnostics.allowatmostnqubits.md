---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Operación AllowAtMostNQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 3aa80767ac0f752e7be0efa2966c580ca3cb8f19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830909"
---
# <a name="allowatmostnqubits-operation"></a>Operación AllowAtMostNQubits

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Entre una llamada a esta operación y su método contiguo, se declara que como máximo un número determinado de qubits adicionales se asignan con instrucciones using.

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Número máximo de qubits que se pueden asignar.


### <a name="message--string"></a>Message: [cadena](xref:microsoft.quantum.lang-ref.string)

Mensaje que se va a mostrar cuando se produzca un error.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Ejemplo

El siguiente fragmento de código producirá un error cuando se ejecute en equipos que admiten este diagnóstico:

```qsharp
within {
    AllowAtMostNQubits(3, "Too many qubits allocated.");
} apply {
    // Fails since this allocates four qubits.
    using (register = Qubit[4]) {
    }
}
```

## <a name="remarks"></a>Observaciones

Esta operación se puede reemplazar por una no operativa en destinos que no la admitan.