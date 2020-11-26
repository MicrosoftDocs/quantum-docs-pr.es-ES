---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operación GetQubitsAvailableToUse
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201417"
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