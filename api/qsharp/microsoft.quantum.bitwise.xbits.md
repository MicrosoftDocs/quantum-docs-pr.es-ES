---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 91619803c7efe56e617b16637f5302aa0b7978ec
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729812"
---
# <a name="xbits-function"></a>XBits función)

Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)

Configura [](https://nuget.org/packages/)


Devuelve un entero que representa los bits X de una matriz de operadores Pauli.

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Entrada

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matriz de operadores Pauli que se va a representar como un entero.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Entero $x $ con la representación binaria $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, donde $p _I = $0 si `paulis[i]` es `PauliI` o `PauliZ` y donde $p _I = $1 si `paulis[i]` es `PauliX` o `PauliY` .

## <a name="remarks"></a>Observaciones

La función producirá una excepción si la longitud de la `paulis` matriz es mayor que 63.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. bit a bit. ZBits](xref:Microsoft.Quantum.Bitwise.ZBits)