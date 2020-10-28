---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operación GetQubitsAvailableToBorrow
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727166"
---
# <a name="getqubitsavailabletoborrow-operation"></a>Operación GetQubitsAvailableToBorrow

Espacio de nombres: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Configura [](https://nuget.org/packages/)


Devuelve el número de qubits disponibles actualmente para tomar prestado.
Esto incluye qubits sin usar; es decir, esto incluye el qubits devuelto por `GetQubitsAvailableToUse` .

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits que se pueden asignar en una `borrowing` instrucción.
Si el equipo de destino que se usa no proporciona esta información, `-1` se devuelve.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Environment. GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)