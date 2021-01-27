---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855206"
---
# <a name="withzeroinsertedat-function"></a>WithZeroInsertedAt función)

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Insertar un bit de 0 en un entero

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>Descripción

Esta operación toma un entero, inserta un 0 en `position` el bit y devuelve el valor actualizado como un entero.  Por ejemplo, si se inserta un 0 en la posición 2 del número 10 (10 $ {10} = 1010_ {2} $), se devuelve el número 18 ($18 _ {10} = 10010_ {2} $).

## <a name="input"></a>Entrada

### <a name="position--int"></a>posición: [int](xref:microsoft.quantum.lang-ref.int)

Posición en la que se inserta 0


### <a name="value--int"></a>valor: [int](xref:microsoft.quantum.lang-ref.int)

Valor que se modifica



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Valor modificado