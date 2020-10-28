---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operación GetQubitsAvailableToUse
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727161"
---
# <a name="getqubitsavailabletouse-operation"></a>Operación GetQubitsAvailableToUse

Espacio de nombres: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Configura [](https://nuget.org/packages/)


Devuelve el número de qubits disponibles actualmente.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits que se pueden asignar en una `using` instrucción.
Si el equipo de destino que se usa no proporciona esta información, `-1` se devuelve.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)