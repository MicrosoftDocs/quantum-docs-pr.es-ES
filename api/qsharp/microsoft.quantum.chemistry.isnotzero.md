---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728126"
---
# <a name="isnotzero-function"></a>IsNotZero función)

Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)

Configura [](https://nuget.org/packages/)


Comprueba si un `Double` número no es aproximadamente cero.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Entrada

### <a name="number--double"></a>número: [doble](xref:microsoft.quantum.lang-ref.double)

Número que se va a comprobar



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

Devuelve true si `number` tiene un valor absoluto mayor que `1e-15` .