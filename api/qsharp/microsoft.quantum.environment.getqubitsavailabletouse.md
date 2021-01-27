---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operación GetQubitsAvailableToUse
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827795"
---
# <a name="getqubitsavailabletouse-operation"></a>Operación GetQubitsAvailableToUse

Espacio de nombres: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devuelve el número de qubits disponibles actualmente.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits que se pueden asignar en una `using` instrucción.
Si el equipo de destino que se usa no proporciona esta información, `-1` se devuelve.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)