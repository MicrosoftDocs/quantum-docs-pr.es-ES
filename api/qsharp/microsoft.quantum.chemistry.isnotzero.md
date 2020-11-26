---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204069"
---
# <a name="isnotzero-function"></a>IsNotZero función)

Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)

Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Comprueba si un `Double` número no es aproximadamente cero.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Entrada

### <a name="number--double"></a>número: [doble](xref:microsoft.quantum.lang-ref.double)

Número que se va a comprobar



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

Devuelve true si `number` tiene un valor absoluto mayor que `1e-15` .