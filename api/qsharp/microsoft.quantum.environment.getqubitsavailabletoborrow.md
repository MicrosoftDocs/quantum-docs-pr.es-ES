---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operación GetQubitsAvailableToBorrow
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853243"
---
# <a name="getqubitsavailabletoborrow-operation"></a>Operación GetQubitsAvailableToBorrow

Espacio de nombres: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devuelve el número de qubits disponibles actualmente para tomar prestado.

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits que se podrían tomar prestado y no se asignarán como parte de una `borrowing` instrucción.
Si el equipo de destino que se usa no proporciona esta información, `-1` se devuelve.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Environment. GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)