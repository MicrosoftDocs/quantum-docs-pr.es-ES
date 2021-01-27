---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839599"
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